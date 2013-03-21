---
layout: post
title: Hypervisor
category: distributed-systems
---

# Hypervisor-based Fault Tolerance <small>T. Bressoud and F. Schneider</small>

This paper presents an alternative to the general methods of providing
fault-tolerant systems: special hardware, special operating system, or
writing it in the application. The problem with hardware-based fault-tolerant
systems is that hardware manufactures general place less emphasis on
fault-tolerant processors, as the market is small, so the speed of available
fault-tolerant systems generals lags quite a bit behind that of general-
purpose hardware.  The problem with operating system support is similar,
as operating systems are very complex, and designing and programming
it to handle redundant hardware is difficult at best, and the system has
to be built for each operating system that is written.  In order to be
able to write the fault-tolerance into the application, either each program
has to be very aware of dealing with faults, or you have to write a
library which knows how to do it, and bottleneck your programmers through it.
  Instead, Bressoud and Schneider propose to implement a virtual machine
on the hardware which understands how to do fault-tolerance.  If the VM
presents to the operating systems a machine that behaves exactly the same
as the underlying hardware, then any operating system that runs on the
original machine runs on the VM.  Moreover, writing a VM for a new hardware
is much more feasible than getting the hardware companies to create the
hardware.
  The virtual machine they wrote to handle fault-tolerance is called
Hypervisor.  They (and this summary) mostly talk about fault-tolerance
with two processors: a primary and its backup, but the system they
describe is easily extensible to multiple backups.  Because of the
nature of their system, they need only one virtual machine to be
running at once (this is contract to IBM's system, which allowed several),
which simplified their efforts quite a bit.
  In order for there system to work, they make several assumptions:

## I/O Device Accessibility Assumption
  I/O devices are shared between virtual machines.  Thus, the disks,
the keyboard, the monitor, etc. can be controlled by any processor.

## Virtual Machine Assumption
  Virtual machines correctly imitate the hardware.  This is fairly
self-explanatory; if the VM's differ from the hardware, the O.S. may
not work.

## Ordinary Instructions Assumption
  An ordinary instruction is one that depends only on the virtual machine
state (which includes memory, contents of registers, etc.).  This is
as opposed to environment instructions, which depend on exterior 
things (time-of-day clock, content of I/O devices, etc.)

  The ordinary instruction assumption states that executing the same
ordinary instruction on two processors in the same virtual machine state
has exactly the same effect.

## Environment Instruction Assumption
  During environment instructions, the virtual machines have a chance
to communicate.  This allows the system to ensure that whatever
information was given the primary is also given to the backups.

## Instruction-Stream Interrupt Assumption
  A mechanism is available to call the hypervisor when a specified point
in the instruction stream is reached.  On the processor they were working
on, it had a counter that counted down by one per instruction, and when
it reached 0, an interrupt was thrown.  Other options include periodic
explicit calls of the hypervisor, among others.
  This assumption allows the introduction of a concept called an 'epoch.'
An epoch is the portion of programs between hypervisor invocations (those
not resulting from environment instruction assumptions).  Epochs must
be the same for all virtual machines for this system to work.

  Given these definitions, they designed a fault-tolerant system, using
only two basic tricks: interrupts are delivered at epochs, and the
result of environment instructions are passed from the primary to the
backup.  Synchronization occurs at epoch breaks.
  The backup always runs one epoch in the past with respect to the
primary.  Thus, at the beginning of the epoch E, the backup has the result
of all environment instructions that it will execute and all of the
interrupts that were delivered to the primary when it started epoch E.
Thus, it is able to execute the next epoch EXACTLY as the primary did.
If the primary failed during epoch E, then the backup will never receive
and "(end, E)" message, and, after a timeout, will recognize that the
primary has failed, then it promotes itself to primary, and, as the primary
failed during its execution of epoch E, it has no responsibility anymore
to behave in the same manner as the primary did.
  The primary ensures that after finishing epoch E, it does not continue
until the backup has received all the messages from that epoch, at which
time it sends an "(end, E)" message to the backup, notifying it that
the backup can start epoch E now, and then the primary starts epoch E+1.

## I/O instruction problem

  The major problem with this system as described is lost interrupts upon
failure.  The backup ignores all interrupts that it receives, secure
in the fact that the primary will tell it if it was really important,
as the primary is executing the same instruction seem, so it should
receive the same interrupts.  However, between failure and the end of the
epoch, the interrupts received by the primary are lost.  Thus, these
must somehow be re-issued.  Hypervisor assumes that all I/O devices
have the ability to issue an 'uncertain interrupt,' telling the
processor that the I/O may or may not have been performed.  Hypervisor
then keeps track of all pending I/O operations, and, upon failure, issues
uncertain interrupts for them.  Since the operating system must be able
to handle these anyway, this method requires no changes to the 
operating system.


## Performance

  Within a reasonable band, the longer the epoch, the better the performance.
They typically looked at epoch lengths no longer than 35,000 instructions.
For small epoch lengths, the processor spends the majority of its time
synching the two processors.  For extremely long epoch lengths, the addition
latency induced by the interrupt delivery method starts to become an issue.
Moreover, for the higher epoch lengths, the speed of communication (10 Mbps
vs 155 Mbps) was no much of an issue.
  The epoch length had a much larger effect on CPU intensive operations,
as the I/O intensive workloads are more bounded by the disk accesses, so
the cost of making sure the two systems are synchronized is lost.  Overall,
the system was 1.5 to 2 times slower than without fault tolerance.

## Post Script
 
  The discovered that the limiting factor in their original system was
ensuring the backup had received all the messages it had sent.  They
relaxed this constraint to forcing the backup to have acknowledged
all messages before the primary issues the next I/O operation.  The
justification for this is that I/O operations are the only way the
state of the I/O device is revealed to the virtual machine.  This
alteration helped immensely in CPU intense operations, increasing the
speed by 50% (taking 33% less time), but, not surprisingly, was not
nearly so helpful on the I/O intense operations.  The revised system
is the one discussed in the previous paragraph.