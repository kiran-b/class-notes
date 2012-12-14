---
layout: post
title: Aron Pilhofer - Making the Most of Digital
categories: talks
---

# Making the Most of Digital<br> <small>Approaches to interactive storytelling</small>

## Background
- nerd-side of journalism
- 2007: created the interactive news team
	- social media team (7 people)
	- community team (10 people)
	- technology dev (18 people)
	- news future: combining these three things
- "most of the things you think are awesome about the NYT: that's not me. Sorry."
- storyforms, social, building thins

### Chicagocrime.org
- one of the first map things
- revolutionary at the time: had to reverse-engineer google maps API
- crime + geography = narrative online
	- or, at least, the ability for the reader to create narrative online

### Washington Post's data-driven interactives
- Congress app: see bills, slice data, etc.
- learn what your member was doing: not a journalist-created narrative

### I-35W bridge
- Aug 1, 2007: bridge collapsed
- part of the computer systems reporting team
- had a DB of all the other bridges in the US with the same construction, built at the same time, etc.
- other news orgs started picking up on this
	- Plain Dealer published a heat map of deficient bridges
	- MSNBC published a state-by-state version of deficient bridges
	- Miami times
- NYT: nothing...
	- venn diagram: overlap between graphics, video, interactive news
	- went to IT diagram: need to be able to do computer-based reporting
	- couldn't move quickly on this: no capability to do this

### NYT interactive news dept
- created the interactive news dept
- coder/journalists + social
- a news desk, not a service desk
	- not a deli counter: don't deal with first-come-first-serve tickets
	- do their own features/interactives
- in and of the newsroom
	- much of the team hadn't stepped foot in a newsroom before
	- not cordoned off as devs/nerds
- capabilities we never had
	- [instagramming the election](http://www.nytimes.com/interactive/2012/11/06/us/politics/instagramming-the-election.html)
	- election maps
- Separation of responsibilities
	- his team munches, crunches, and spits out pretty data
	- graphics, interactives pick this up and deal with it (election data delivery is awful)

## Future

### Lies outside of the CMS <small>break the template to fix it</small>
- "NYT is a department store model. We're Macy's. We have Levi's jeans, but you can't find it"
	- idea of destinations
	- "dirty little secret of section fronts: no one goes there"
- addictive games feature
- politics/election dashboard
- NYT: can't change the layout of most pages
	- takes 3 weeks to change the links
	- fixed layout
- what you don't change: "We wanted to feel classy."

#### [Olympics section front](http://london2012.nytimes.com/)
- have to build things that works with the data and content
- can't use the same layout as politics to do this
- naming issue: "olympics hub," not section front
- swapped the column layout
- "A column," "B column," "C column"
- intermingling new data, stories, photos, interactives
	- updating dynamically to watch the games

#### [SchoolBook](http://www.schoolbook.org/)
- "NYT has a reputation for not covering NY"
- not true: just doesn't make it to the front page, so it's never seen
- goal: get people to educational coverage
- three things: news, conversation, and data
- deliberately looks nothing like the NYT
- built all sorts of tools
	- so much school data out there, really hard for a normal person to parse
	- came up with index scores: satisfaction, enrollment, performance, diversity
- journalists are data interpreters and indexers

#### Moderation
- community element: reader discussions as first-class content
	- no "voice of god" reporters
	- Q&A style modeled after quora
- community design was pretty remarkable: only had to ban one person
	- super-high moderation standards: "more letter to the editor than HuffPo"
	- "not a dis: always had these very straightforward content/moderation standards"
- reasonable, off-topic things get rejected
- "nothing on SchoolBook was pre-moderated"

### If you're not building for mobile <small>you're building for the past</small>
- "building for mobile is a massive pain in the ass...it's tripled our workflow"
- like computing in the 1980s: no standards
- "no one is cheering harder than the kindle fire and surface to fail than I am. God forbid we have to do this across tablet."
- could see RWD being a "huger" problem in the future

### Readers Expect Interactivity

#### Election Mood WordCloud
- crowd-sourced person on the street story
	- "most news-free day of the election season is election day. all you have to report is the candidate waving, kissing baby, etc."
	- "pregnant pause before things start happening. You want to do something, what do you do? You go out and talk to people"
	- mood timestamped and color-coded by supporters
- converging on words: dropdown that suggested 30 words
	- 10 negative, 10 neutral, 10 very positive, plus free-form
	- endless debate about ordering of words
	- mixing them up algorithm: "way over-engineered"
	- used this word list for tons of other interactives

"blowing up the form of journalism and putting it back together in an interactive way"
"creating pieces of journalism out of a conversation with readers"

#### Conversation with Readers
- Challenge of videos
	- people will only watch videos if they are really really motivated

#### debate night dashboard
- repurposed this dashboard for debate night, hurricane, etc.
- live fact-checking:
	- readers put together questions and upvote them
	- staffers go in and answer this
	- "deriving first-class content from reader questions"
- "this dashboard has become a story form for us"
- vs. traditional form: the lead on
	- keep updating the story as you go. CNN still does this.
	- no sense of importance, recency, or interactivity
- this dashboard has highlights, interactivity, and reverse chron blog-style feed
- ex: hurricane hits NYC
	- could keep doing lead-ons
	- multi-day events: you end up with discrete news stories for events (very old media)
	- want a canonical URL to send people to: here is our Sandy coverage
- "sections themselves are sort of antiquated...remix content online in a way that doesn't map to newspapers"

### Social is a Second Home Page <small>though it's rarely treated as such</small>

#### Oscar coverage
- "the Oscars are huge for the NYT. it's like our Super Bowl"
- three-act app
	- create a ballot online
	- invite friends to your ballot
	- score the ballot live
- dashboard similar to the debate dashboard: like a live blog
	- bring your dashboard into the dashboard: very personalized
	- our attempt at a second screen
- idea: redo on Facebook
	- bring the existing community of FB into NYT
	- log in with FB and bring in anyone who filled out a ballot into your group. also incredibly shareable.
	- seamless community integration
- social team difference: sharing my pick, not sharing a generic ballot
- "this is what news organizations do wrong all the time. Nobody gives a crap that the NYT created a ballot. Nobody's going to share that. They will share their own ballot"

- performance: sharing went up 4x with social integration
- "nobody's going to section fronts and seeing ballots. it's all from FB."

## Q&A
- discovery of news
	- lots of growth through social
	- referrals from search has really flattened out

- archival worries?
	- no proprietary formats
	- can convert everything to modern land
	- "thank god for the iPad. it was the final straw for flash."

### Breaking news
- "being in a newsroom can be fatal for Type A people"
- "it is organized chaos. There is no playbook"
- tried to do breaking apps, but they've sucked
- "create a utility belt. It's like Batman: pull out the right tools to put something together."
	- "like an erector set. don't have anything structured: no SWAT team, etc."
- Sandy was kind of a nightmare: first time we did a dashboard outside of politics
	- lots of undocumented code and black magic
- what we learned: we do need some sort of SWAT team
	- journalist-devs who know how dashboards are supposed to work
- Fiscal Cliff dashboard
	- "dashboards are not meant to be blogs"
	- started off writing 1200 words: not the right story for this form

### Long-form stories
- physical paper: "yesterday's home page"
- long-form version on the paper: 18K words
- long-form on the web: "either going to annoy you or blow your mind"
- experimenting with a new format for long-form on the web: email aron@newyorktimes.com with thoughts

### Three major problems
- analytics
	- looking into better newsroom analytics
	- integrating a Knight-Mozilla fellow 
	- "finding the missing metric": page views is an insufficient number (Justin Bieber vs. Walmart story)
- forms for breaking news
	- Mother Jones explainers during Arab Spring
	- genius form: between a Q&A and FAQ
	- series of news events that aggregate into a single story
	- solves both immediacy and context
- automation and filtering
	- some sort of crazy filter or change detection mechanism in place
	- fancy if-this-then-that
	- anomaly detection: not something newsrooms are really doing
	- the LA Times is doing this in very basic ways
	- especially interesting for congress
