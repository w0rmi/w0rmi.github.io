---
title: "My Turnip Merge Quest: Finding the North Star"
date: 2026-02-27
description: Hey there, earthling! 
tags:
  - MyTurnipMergeQuest
  - turnip
  - mesa3d
  - driver
  - linux
  - android
  - tutorial
image: "[[https://images.unsplash.com/photo-1516571748831-5d81767b788d?q=80&w=774&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D]]"
imageOG: true
hideCoverImage: true
hideTOC: false
targetKeyword: mtmq northStar
draft: false
---

![alt](https://images.unsplash.com/photo-1521929253990-8dccb82cc59b?q=80&w=1740&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)

Hey there, earthling! In this section I want to talk about how to choose an open-source project. Since there is a sea of options, it can be a little (or a lot) overwhelming. I'll share my own experience, which obviously will differ from yours, and how I ended up choosing Turnip. It may give you some heuristic from where to start and how to go about it. I'll try to keep some parts general, while others will be more specific to my personal path. Hope this helps you! :)

# Step 1: Zoom Out

![alt](https://images.pexels.com/photos/28934343/pexels-photo-28934343.jpeg)

Spot something that you are interested in, BUT in an **abstract way**. I'm not asking you to pick something super specific like: *"I AM INTERESTED IN PROFILING THE PERFORMANCE OF RAY TRACING CALLS IN MOBILE GAMES"* -> No e.e! We'll have time for that later. Think more like: *"I am interested in computer graphics"*.

To help you narrow it down, you have 2 options; either you pick something you have **absolutely no idea about but interestes you and you want to make a big YOLO** on that curiosity, or you pick something where you **already have some experience(even if it's just 'close-enough') and interest**. In my case, I picked **Computer Graphics** because I'm really interested in it and already I have some background.

# Step 2: Zoom In

![alt](https://images.unsplash.com/photo-1610023709594-b3a7b76331d2?q=80&w=1740&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)

Now that you have an **abstact idea** of what you want, in order to know specifically which project to choose, we have to do a deeper research. Since we are talking about open-source projects only, I'll share what worked for me. You can do your own research in any way that you can think of, but if you need some help, this is where I started looking at:

## OSS Conferences

Chill, I'm not telling you to go to any OSS conference (yet!). I'm saying that one way to find interesting OSS projects is to type into your preferred search engine or YT -> "are of interest + open source conferences". In my case, it was "computer graphics + open source conferences". From here, start putting ass-hours (just sit and read/watch :v). Research, read and watch whatever sparks your curiosity. I know that most of the stuff would be **"yada yada yada"**, but that's ok! It's part of discovering new things and getting started in this world :)

Looking at it this way, you will probably find the latest state of OSS in that specific area. It's important to notice that in these conferences you will find more "big" open-source projects, which can be good or bad depending of what you are looking for. Either way, it will give you an idea in what people are working on lately. In my case I found really interesting talks related to Computer Graphics in these conferences:

### X.Org Developer's Conference (XDC)

![alt](https://cdn.masto.host/floss/media_attachments/files/115/298/467/746/117/325/original/a3776f98a0d3b33a.jpg)

### FOSDEM

![alt](https://assets.chaos.social/media_attachments/files/115/996/449/614/589/653/original/8f653920353496c7.jpg)

### Vulkanised

![alt](https://cdn.fosstodon.org/media_attachments/files/116/098/107/433/375/879/original/a97ccd92f2ac2f0b.jpg)

### The Linux Foundation Open Source Summit

![alt](https://www.linuxfoundation.org/hs-fs/hubfs/Sched%20Mobile%20Header.png?width=911&height=380&name=Sched%20Mobile%20Header.png)



## Code Hosting Platforms

The title describes itself, choose any platform, type the area that you are interested in and pay attention to the license, to check if it's OSS. Here, you will probably find more small open-source projects that in the other way. 

Examples:

- gitlab.com
- SourceHut
- codeberg
- https://github.com/
- bitbucket.com

# Step 3: Pick Your Pokemon

I imagine that now you have some more specific idea of what interests, now it's time to choose very specifically! In my case I got really interested in the actual state of the open-source graphics drivers on linux, there is a lot of people involved lately. For my surprise, it was a lot more advaced that I though, since I remember some years ago to try gaiming on linux at it had a loot of room for improvement, but now, WOW. The news that I've been reading are completely true, linux for gaming right now is wonderfull, I always had/have in pc 2 partitions one with linux for my projects/work and the other with windows only for gaming for the lack of stability. It's very exciting to see a lot of people apporting and improving this, when I saw all of this I definitely knew that I wanted to formar parte.

Ok, I know that I want to aport to open-source graphics drivers, but which one? There is a loooooooot of drivers. I started comparing each of them to know which one to pick. At that time I made this graph(it will proably be outdated at the time that I publish this):

FOTO

Like you can see in the table, a lot of options. I'll get very personal now, since this were my preferences to pick one or another:

- Something that is more related to modern graphics, so I would prefere Vulkan.
- Something that people are involve and it's not something death, since I want to belong to some kind of developers community, in which I can get and give help.
- Something that is not completely "done" and also not completely "new", since in any of those states, it would be hard for me since I'm starting, it has to be something in the middle.
- Something that I already have the hardware to work with or it's cheap to buy.

I starting looking on communities and subreddit how alive was the project, and also checked each repo to see the "movements" of their developers. With all these preferences, I got this options:

FOTO 2

At the time that I was choosing which one to pick in, I remember that I joined the subreddit of android emulation and I got impressed as how many users where testing games on Android and how well they are running and at the same time Valve have announced the Steam Frame that would use an Adreno GPU that means a mobile gpu. At that moment I knew that I would pick Turnip as my first open-source project. 



