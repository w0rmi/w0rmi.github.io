---
title: "My Journey Learning Graphics Drivers: Day Zero"
category: "MyJourneyLearningGraphicsDrivers"
order: 0
date: 2025-11-16
description: Hey! Welcome to my series of blogs in which I document my journey venturing into the world of graphics drivers.
tags:
  - MyJourneyLearningGraphicsDrivers
  - mesa3d
  - driver
  - linux
  - gpu
  - blog
image: "[[https://images.unsplash.com/photo-1452421822248-d4c2b47f0c81?q=80&w=1548&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D]]"
imageOG: true
hideCoverImage: true
hideTOC: false
targetKeyword: mjlgd dayZero
draft: false
---
<center>

# Day Zero

</center>

![alt](https://images.unsplash.com/photo-1452421822248-d4c2b47f0c81?q=80&w=1548&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)

*Image from [Dariusz Sankowski](https://unsplash.com/@dariuszsankowski) - [Unsplash](https://unsplash.com/)*

**Heeey!** I just moved to a new country with my wife and cat. There is a lot going on lately for us, but we're very happy with the new life so far :) In order to relocate, I gave up my last job, and now we're completing all the boring paperwork and handling all other stuff needed after moving. Being a little bit more settled down in our new home, let's say that I've some time left to incursion into what I really wanted to for such a long period of time, which is **graphics drivers**!

This is my fourth attempt at refactoring this blog...I just overthink things too much, and it's well known that "overthinking" = "doing nothing", so here we go again. I'd written more or less 5 posts about my incursion in graphics drivers, which I never published publicly because of my Achilles heel that I mentioned. This time, finally, I plan to publish them(and more), but refactored by this type of writing, which is more relaxed. The previous posts were something in between a blog and a tutorial, which I didn't enjoy writing. I realized that I much prefer the blog type.

I decided to just write what comes from my heart and soul. I hope you like it or find something valuable here, you are more than welcome to come with me on this new journey, I left you a spot :)

---

## Who It's For

![](https://images.unsplash.com/photo-1700838712765-fad192553296?q=80&w=1760&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Claudio Schwarz](https://unsplash.com/@purzlbaum) - [Unsplash](https://unsplash.com/)*

In this era of AI slop, misinformation, major layoffs, and vibecoding, I consider it super valuable when people share original, souled and inspiring content. The kind that feels human, is easy to read, and makes this moving and hard present a little bit brighter, which is much needed nowadays. That's why, inspired by those people, I want to try to do the same and share, hopefully, exactly that. If this resonates with you, welcome :)

The main focus will be oriented more to complete beginners, people interested in graphics driver in general, or simply lovely, curious people.

---

## Goal

![alt](https://images.unsplash.com/photo-1534447677768-be436bb09401?q=80&w=1788&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Joel Vodell](https://unsplash.com/@joelvodell) - [Unsplash](https://unsplash.com/)*

I can't say that there aren't posts/blogs from people who talk about graphics drivers, since there are many professionals in the open source world who share very valuable information about them, but I can say that there are almost(if any..) no posts/blogs by people sharing their complete journey of how they got into graphics drivers, what they did to get in, what they had to learn, the struggles and beauties of the area, and so on. That's why I want to document my journey and see where it goes.

In short, the content in this series would be only related to open source **GPU drivers**, starting completely from scratch, studying and exploring the fundamentals until I hopefully make my first merge request into one of the **Mesa** drivers.

---

## Where We Stand

![alt](https://images.unsplash.com/photo-1556191325-0e553d4de1fb?q=80&w=1331&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Timon Wanner](https://unsplash.com/@77timon) - [Unsplash](https://unsplash.com/)*

Well, since the goal is related to open source GPU drivers, this means **Goal = GPU Drivers + ComputerGraphics + Linux** I don't start completely from 0, since I'm a **Graphics Programmer** with some years of experience and I also have experience in **Linux**, but very little about GPU drivers, which I got really interested in the last year. I've some reading of blogs and articles on my back, but 0 real experience. The point of telling you this is because I want to be honest about where I'm starting from. My hope is that maybe you find yourself in a similar position, trying to do something similar, and this can inspire you to start learning too. If I can achieve the goal starting from here, you can definitely do it too.

See you next week hopefully!
