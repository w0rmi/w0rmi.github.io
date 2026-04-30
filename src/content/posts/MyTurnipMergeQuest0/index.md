---
title: "My Turnip Merge Quest: Day Zero"
category: "MyTurnipMergeQuest"
order: 0
description: Hey there, earthling! Welcome to my series of blogs/tutorials related to contrubuting to the Turnip driver from Mesa.
tags:
  - MyTurnipMergeQuest
  - turnip
  - mesa3d
  - driver
  - linux
  - android
  - tutorial
image: "[[https://images.unsplash.com/photo-1682685795463-0674c065f315?q=80&w=1452&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D]]"
imageOG: true
hideCoverImage: true
hideTOC: false
targetKeyword: mtmq dayZero
draft: false
---

<center>

# Day Zero

![alt](https://images.unsplash.com/photo-1682685795463-0674c065f315?q=80&w=1452&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [NEOM](https://unsplash.com/@neom) - [Unsplash](https://unsplash.com/)*

**Hey there, earthling!**  Welcome to my series of posts/tutorials (I hope to make many of them... at least enough to call it a series e.e). I plan to share the knowledge I'll be gathering along this journey as I make my first contribution to the open-source world, specifically to the **Mesa-Turnip** project.

I'm very excited to start this path. I've wanted to get involved in this world for quite a while, but for some reason or another, I just didn't. But hey, here I am, better late than never! :)

</center>

---

## Who It's For

![](https://images.unsplash.com/photo-1700838712765-fad192553296?q=80&w=1760&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Claudio Schwarz](https://unsplash.com/@purzlbaum) - [Unsplash](https://unsplash.com/)*

The world of **OSS** moves fast, really fast. As time passes, it moves faster, which can be a bit scary (for me and probably for you too). This makes us, simple humans, feel lost and not know where the @#$ to start, what to do, how, which project to pick, etc.

My hope for this series is just to share my own path, showing how I started, where, my mistakes, my victories, and hopefully, my first real contribution, in hope of inspiring others too. In this case, focusing specifically on **Turnip**. This series is also for me, sharing it with you will help me stay motivated on this long path by recharging my mana to keep going **:3**.

---

## Goal

![alt](https://images.unsplash.com/photo-1534447677768-be436bb09401?q=80&w=1788&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Joel Vodell](https://unsplash.com/@joelvodell) - [Unsplash](https://unsplash.com/)*

As you can see in the title, my goal is to make my first merge request into the **Turnip** driver project from **Mesa**. Obviously, I want to make a relevant one, like a bug fix or some tool that can help others, not just a typo fix (without discrediting those fixes!). I know this is an ambitious goal for someone who has never contributed to any OSS project and also doesn't have any driver experience...., but I'm very excited to get into it. Every journey has to begin somewhere :)


> [!note] What Is Turnip?
> Turnip, in short, is an open source Vulkan Linux driver for the Qualcomm Adreno GPUs. It is used mostly by Android users through emulators :), since those GPUs are presented mostly on mobile/tablet devices. Also, it's present on VR headsets, now also on the new Snapdragon laptops, and in other less relevant devices. It's also part of the Mesa project, the most important library for graphics on Linux 100% OSS! Freedreno it's his father(?) since a lot of the code is based on it. Freedreno includes the OpenGL driver.

I'll get into a lot of different details, such as why I chose it as my first OSS contribution, in my future posts.

---

## Where We Stand

![alt](https://images.unsplash.com/photo-1556191325-0e553d4de1fb?q=80&w=1331&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Timon Wanner](https://unsplash.com/@77timon) - [Unsplash](https://unsplash.com/)*

Well, since the goal is related to **Turnip** and **Turnip = Drivers + ComputerGraphics + Linux** I don't start completely from 0, since I'm a **Graphics Programmer** with some years of experience and I also have experience in **Linux**, but for the other part...the part of **GPU** drivers, I got really interested in the last year, so I have some reading of blogs and articles on my back, but 0 experience and **Android**..... -1. Why do I tell you this (which you probably don't care...)? Well, I just want to be honest about where I'm starting from. My hope is that maybe you find yourself in a similar position as me trying to do the same. If I can achieve this starting from here, you can definetely do it too!

