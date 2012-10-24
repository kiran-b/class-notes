---
layout: post
title: Scalable Backbone Apps
categories: talks
---

# Scalable Backbone apps
- stack: coffeescript, haml, etc

## why backbone
- MV\*
- RESTful API support
- easy integration w/Rails backend

### BUT
- toolset,not framework
- not opinionated (no established patterns)

## MVP style
- one router, no logic (single responsibility: router routes)
- backbone models/collections (plus relationmodel, etc)
- Views (HTML)
	- dumb, not backbone views
	- y/n do I show this
- Presenters (backbone.view)
	- don't share logic w/routers
	- listen to view events, etc

## App structure
- (pull in image from slide)
- app: router, helpers, directors
	- use helpers for some data munging, etc. still trying to figure out responsibility b/w views, helpers, models.
- directors: MVP

## Maintainability
### test everything!
- Jasmine
- BDD: clarify the thought, minimize risk, document functionality
- phantomJS
- CI

### Prototypes and chaining
- modular code, yo
- singular responsibility
- less than 100 lines/class or method

### Composite architecture
- [Backbone Marionnette](https://github.com/marionettejs/backbone.marionette)
- building blocks
- limited dependencies, functionality, responsibility

### Backbone.StateManager
- [github repo](https://github.com/crashlytics/backbone.statemanager)
- web apps are stateful
- lose the conditional statements
- define entrance, exit, transitions in a single state declaration
- use this on UI components, models, collections, etc.

### Namespace and file structure
- one object per file
- file names === object names
- directory structure maps to namespace

### Automation
- compilers and watchers
- scaffolding/generating
- asset management
- npm, rails, grunt, etc.

## Q/A
- why coffeescript?
	- Ruby-esque
	- dangers with abstracted languages: what is it doing?!?
	- read outputted code, yo
	- pros outweight cons only as long as you actually read the damned code
- wtf is the statemanager
	- make the router dumb
	- flexible in how you determine states
	- hold onto states like: are we showing single pages? multiple stats?
	- UI element like a dropdown: use statemanager to determine what states are selected
- followup: separation b/w models and statemanager
	- play-by-ear
	- no opinion
	- models do hold on to states
- client/server data management
	- woo memory leaks
	- only maintain a certain number of crash data in client-side collections
	- backbone relational holds onto data it shouldn't