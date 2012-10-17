---
layout: post
title: Propublica - Software is Rebooting Journalism
categories: talks
---

# Software is Rebooting Journalism<br> <small>Data Mining and Visualization in the Public Interest</small>

## News Applications
- making journalism using SW instead of words and pictures


## brief history of data journalism
- been around for over a century: publishing data and tables in papers
- stock tables
- 1821 piece on quantizing child poverty
- 1876 sports scores
- 1896 [NYT front page](http://www.ericson.net/content/wp-content/uploads/2010/11/1896-full-page-1000-337x400.png): tables and stats on election results
	- mildly incorrect...
- 1952: CBS uses Univac to predict the election from polls data
	- [predicted correct result](http://www.wired.com/science/discoveries/news/2008/11/dayintech_1104), but didn't air it
- 1973: data tables precinct by precinct on race, crime, etc.
	- published full tables and maps

## Today
- "imagine a growing and thriving culture of data in newsrooms."
- django
- [chicago crime project](http://chicago.everyblock.com/crime/)
	- freely browsable database of crimes reported in Chicago

## Part 1: Attributes of a News Application
### Contextualizes
- what's it got to do with me?
- how does it relate to other pieces of data?
- demo: [opportunity gap](http://projects.propublica.org/schools/)
	- distribution of educational opportunities along various lines
		- AP classes, higher math, and higher chemistry
	- helping people look for access to opprotunities

### Remixable
- expose the data to people in a ton of different ways
- demo: [Politifact](politifact.com)
	- has a great CMS for journalists
- demo: PAC Track

### Durable
- stay interesting a week later
- difficulty: how do you keep something like that up to date? keep pulling relevant data?
- difficulty with technology: how do you keep the web apps online?
	- make raw data available, even if the app goes down
- ex: [Dollars for Docs](http://projects.propublica.org/docdollars/)
	- lets you check whether your doctor takes money from pharmaceuticals

### Generative
- generate other journalism
- Propublica's happy if another newsorg picks up their data for a story
- ex: doctor data allowed the Boston Globe to put together a few front-page pieces on the data
	- one national app -> 124 local stories

## Demos!
- [Unemployment trust fund](http://projects.propublica.org/unemployment/)
	- models unemployment data by state
	- "tomorrow's news today"
- [Message Machine](http://projects.propublica.org/emails/)
	- NLP and clustering to analyze subtle differences in Obama and Romney campaign emails
	- Obama campaign easier to model than the Romney
	- pop culture and colloquial terms definitely show through depending on age group
	- "a lot of what used to be obvious about campaigns is now unobvious. Giantish data sets make this hard."
	- "start to help people understand the methodologies used in modern campaigns"

## Open Source Code
- open source tools, not whole news apps
	- stateface: US state typeface
	- timeline-setter

## Q&As
- made a recovery.gov app based off of data.gov info
- why aren't there more of these things?
	- structure of newsrooms still not great for this. tend to repel this sort of thing.
	- still people in the newsroom who don't have the ability to work with databases, command line tools, etc.
	- could benefit from a Build-your-own-news-app app: some sort of simple CMS for non-programmer journalists
	- pair hacker and journalist
