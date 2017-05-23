---
layout: post
title: Weekly Review
description: "Weekly research recap"
permalink: /weekly-review/2015-12-05
categories: [weekly-recap, research]
tags: [research, conference]
share: false
---

## Exec Summary:
  - Attended Joel Sadler's defense.
  - Experimented with Mozilla Thimble. Really impressed.
  - Started researching ARToolkit. Implementation in progress.
  - Emailed Paulo Blikstein but nothing yet...
  - Received feedback on Relatable Programming and revised first 3 chapters.

----

## Research

#### AR for Design Blocks

<figure>
  <img src="/assets/img/ar_working.png">
  <figcaption>Getting the new computer vision to work.</figcaption>
</figure>

After doing some user testing over the Thanksgiving break, I came to the conclusion that using solely color for computer vision isn't a great solution going forward. I found a ARToolkit that had been ported to Javascript and worked on getting it hooked up to my system.

#### Thimble

My introduction to Thimble came about because Thomas Park's <a href="http://flexboxfroggy.com/">game to teach Flex CSS</a> was trending on Hacker News. His tutorial was really fun and helped me actually learn some of the basics of flexbox (which I've been curious about for awhile). I anticipate flexbox being a major disruptor to the current layout practices. It's supported by all major browsers except IE (no surprise there), so it's becoming safer to use.

When I finished the game, I checked out more of Thomas' work and that's where I came across <a href="http://thimble.mozilla.com">Thimble</a>. Thimble is very similar to the editor I worked on <a href="http://vanilla.meteor.com">Vanilla</a> (be patient, it takes a couple minutes to bootup the first time). Thimble is much better than my early prototype and I'm currently thinking about ways that I could extend it and make it better. I really like how Thimble shows what part of the live page you are modifying as you move the mouse cursor about. It even works when make CSS changes which I found really impressive.

<figure>
  <img src="/assets/img/thimble.png">
  <figcaption>Mozilla Thimble</figcaption>
</figure>

This editor makes me think about Bret Victor's work. I think there's more that can be done in this space to tie code and visuals together more seamlessly.

#### Relatable Programming

I got some feedback from a couple of people this week that read the first 3.5 chapters of the book. The feedback was really positive. One of the reviewers told me that he gets intimidated when he hears programming terminology (like variable), but the visual representations of those ideas has been extremely helpful.

<figure>
  <img src="/assets/img/relatable_programming_editor.png">
  <figcaption>New code editor styling</figcaption>
</figure>

He confirmed my hunch that adding more styling to the code editor would be even more helpful. I used the feedback to redo portions of the first 3 chapters and provide even more visualizations.

#### Reviewed Related Work

<figure>
  <img src="/assets/img/k-sketch.png">
  <figcaption>K-Sketch</figcaption>
</figure>

Spent some time playing with K-Sketch. It makes me think a lot of Adobe Flash and tweening.

<figure>
  <img src="/assets/img/activity_designer.png">
  <figcaption>Activity Designer by Yang Li</figcaption>
</figure>

This tool is very visually unappealing, but I do find the functionality impressive. I like the flexibility of the IFTTT language it supports. I'd be curious to know what's the spectrum of apps that can be built with Activity Designer and how far out is the complexity cliff.

----

## Classes

Attended Tesla. I had just finished reading Elon Musks' book (and I've always been somewhat of a fanboy) so it was fun to get to hear from people that worked at the company. I wasn't overly impressed with the people, but I wasn't unimpressed. They just didn't carry the same confidence that Johnathon did at AirBnB or Rousseou at Facebook. I did like how they brought in a lot of people to talk to us. By the end, there were 6 people answering questions.

----

## Professional Development / Misc.

I attended Joel Sadler's defense. We'd met recently and he'd given me this thoughts on my design blocks project. He did a good job and I was surprised by how casual the actual event was. It was in the d.school.

This week I also read the PhD Grind by Phillip Guo. A lot of it resonated with me. This quarter has been somewhat of a struggle as I've spent a lot of time brainstorming without really making great progress on an idea. I did finally push ahead with design blocks around week 6 and that has been really helpful in understanding my interests and the project better, but now I feel like I'm back in the brainstorming stage.

Watched a talk Michael sent out entitled <a href="http://iesg.eecs.berkeley.edu/Colloquium/2015/D_Patterson_EECS_Colloquium_20151118.mp4">“How to have a bad career in research”</a> by Dave Patterson.

  - I really liked his idea of having 3 ToDo lists. A daily list, a weekly list and a 6-month list.
  - Figure out your own productivity cycle and use it to your advantage. If you're most productive in the morning, don't take care of your emails in the morning.
  - Change the way people do computer science and engineering.
  - Best results are obvious in retrospect.
  - Twice a year, 3 day retreat.
  - Dedicated Friday afternoon to think deep thoughts.
  - People count the projects you finish, not the ones you start.
  - Maximize personal happiness over personal wealth. Family first.
  - Winning as a team vs winning as an individual.

I've been using Meteor for my development lately, but I'm worried that it doesn't scale very well. Someone described it as the microwave of development. I think the analogy is spot in. Meteor makes it really easy to quickly bring something up to speed. For something that scales better though, I've been eyeing the Phoenix Framework. It uses a language called Elixir, which compiles to Erlang which has been battle tested in the phone company world. It's also used by WhatsApp and is showing incredible numbers for the number of connections it can handle.

So I dug into it a little bit. Unfortunately it is rather complicated and there is a lot to learn. It is patterned after Rails which unfortunately I don't really like. Much of that dislike probably is due to inexperience, but anytime I've tried to learn Rails, I just get frustrated with all of the generators and magic keywords that are littered everywhere.
