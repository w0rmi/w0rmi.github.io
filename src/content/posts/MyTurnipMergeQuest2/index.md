---
title: "My Turnip Merge Quest: Leaving the Shire (First Steps)"
category: "MyTurnipMergeQuest"
order: 2
date: 2025-12-05
description: "Hey there, earthling! Welcome to my series of blogs/tutorials related to contrubuting to the Turnip driver from Mesa."
tags:
  - MyTurnipMergeQuest
  - turnip
  - mesa3d
  - driver
  - linux
  - android
  - tutorial
image: "[[https://images.unsplash.com/photo-1738998725908-43c8ab741913?q=80&w=1331&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D]]"
imageOG: true
hideCoverImage: true
hideTOC: false
targetKeyword: mtmq dayZero
draft: false
---
![alt](https://images.unsplash.com/photo-1738998725908-43c8ab741913?q=80&w=1331&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [DJ](https://unsplash.com/@djthoms) - [Unsplash](https://unsplash.com/)*

Probably this blog will be long, so have patience with it e.e. My plan for this blog is to share my setup and help you to leave everything ready to develop comfortably on Turnip, and this means connecting with other developers/communities that will help you through this journey (by gathering info and help), why and how to choose one or another hardware for Turnip, how to configure and leave the hardware prepared for development, and also how to set up Turnip on that hardware. Like I've already mentioned in previous blogs, ***I'm sharing my own journey in hopes to helping others. This may or may not be the optimal way, it's simply my way.***

## Communication

[[https://images.unsplash.com/photo-1568258805731-c117485e50c2?q=80&w=772&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D]]
*Image from [Sandra Tan](https://unsplash.com/@sandratansh) - [Unsplash](https://unsplash.com/)*

First things first, we need to connect with the people working on the project obviously! I think one important aspect of working on an OSS project is to get involved and participate, so that's what we'll try to do.
These are the communications means that I found, but please if you know any other, share it with me and I'll update the list.

### IRC

I won't explain in detail what it is, nor how to set it up, there are a lot of better tutorials for that. But, basically it's a text only chat, where you need an IRC client to connect to any network. In my case, I use Halloy, which works great.

[[halloy.png]]
*Halloy*


The server and channels used by or relevant to the Turnip developers are:

| Server    | irc.oftc.net           |
| --------- | ---------------------- |
| Channels  | freedreno && dri-devel |

To find old chats, you can check this website:

https://dri.freedesktop.org/~cbrill/dri-log/index.php

### Mailing List

It's a subscription mailing list in which you can ask and answer questions. The discussions will be received weekly? by all the the developers subscribed. I think it's relevant to know the latest discussions and also to ask for help if needed.

More info here:

https://docs.mesa3d.org/lists.html

To find old messages, you can check this website:

https://lists.freedesktop.org/archives/mesa-dev/

## Resources

Very helpful to gather information, tutorials and resources that will help us along the way. These are the ones that I could find:

### Official Documentation and Code

Obviously the most important documentation is the official one. Sadly, it has some outdated information, but it is nevertheless still very relevant.

https://docs.mesa3d.org/drivers/freedreno.html

### Tutorials

#### Danylo Piliaiev Tutorials

Extremely helpful and also they are made by one of the main developers of Turnip. In their blog, they share info on how to debug Turnip.

https://blogs.igalia.com/dpiliaiev/turnips-in-the-wild-part-1/


#### Lucas Francisco Fryzek Tutorials

Same, very helpful tutorials, in this case made and shared by Lucas, another important developer from Igalia. 

https://fryzekconcepts.com/index.html


#### Conference Speeches

Like I already shared on this blog [[]], there are several conferences related to the graphic stack. If you search X conference + Turnip or Vulkan, you will find a lot of speeches with a lot of helpful information. I'll not share them all here since there are a lot and depending on what specifically you are working on, you will need one or another, but I thought it was important to mention it.


## Choosing the Right Hardware

Like I already described in the [[first blog]], Turnip is a driver used for Adreno devices. Adreno is present in several mobiles, tablets, and also laptops. So... which one to pick? I don't think there is just one answer, so it depends... In my case I use these heuristics:

- The older the hardware, the more likely it has better support, and better support = less need for development = fewer developers.
- Better support also means = less room for fixing, so the things to improve would be harder to catch (probably) and harder for newer developers like me (and maybe you?).

Knowing that these heuristics have something of truth, we can make the next conclusion:

> We need to pick a hardware that is not very old and is still relevant today.

Ok, but ===what happens if it's new, like the X2 Adreno GPUs?=== At the time that I'm writing this, they came out like a week ago. They will probably have a lot of bugs and a lot of room for improvement. But for a new developer, would this be ok? I dont think so. If you can't properly set up a basic setup or have a more or less stable ground to test things, it would be really hard probably for a new developer.

So... based on this new heuristic, I would need to pick up something that is:

> Neither old nor fresh out of the oven e.e

> Like all things in life...something in the middle. But which one?

These are the Adreno GPUs available and the years in which they have been released:

/....

Ok, something in the middle, let's see what people are using! If more people are using it, it is probably relevant and means more developers working on it.

Like I already mentioned in the other blog, the subreddits related to emulation are full of people trying very cool stuff on mobiles. So I started exploring what were the most used devices and came to the conclusion that the Snapdragon 8 Gen 3 GPUs were very used lately.

Ok, that series seems like "the middle", but the info that made me decide which one was the Steam Frame. That device was announced at the end of last year, saying that they will use... YES, an Adreno GPU, and that Adreno GPU is the 750 one. Done, decision made ;) .This means that it will become more relevant than it's now, and a lot more users will use it. Perfect!

STEAM FRAME

> The Adreno 750 GPU is in different devices: mobiles, tablets and on development boards.

Depending on your budget and preferences, you will choose one or another. In my case, I wanted something cheap and also that would be easy to debug.

. In the case of the development board, it is the most confortable one to develop but very expensive, so I discarded it.
. Mobile vs tablet: well, I would like something that is easier to see glitches and errors, so this measn bigger screen = tablet. 

Since I already had the GPU model and the type of device, the brand didn't matter in my case, so I searched for the cheapest option. In this case ***I chose the OnePlus Pad 2**.

FOTO PAMPU
* My cat bendiciendo para que pueda cumplir mi quest

Luckily, I could get a very cheap second hand one here in Germany.

> [!important]
> Important to mention! Since I chose a GPU that is used on Android devices, some explanations will be specific to Android (at least at the beginning of the series). In the future, I plan to develop on the Adreno X1 GPUs, but only after I finish this quest. Since debugging on those laptops is easier than on Android, but with the current prices, I'll wait e.e.

> [!important]
> Important to mention! Search for a device that is easy to root. This means that the manufacturer provides documentation on how to unlock the bootloader. In the case of the OnePlus, it is a perfect choise."

## Leaving Everything Ready for Turnip

You have two options for using Turnip on Android: either you use it internally through an emulator, or you use the driver in the whole OS. The latter option is better since debugging through an emulator would be painful.

Changing the graphic driver in our Android OS is not so easy as in Linux, but neither it is too hard (for now...). I'll share what I did to leave my tablet ready for using Turnip.

### Rooting the Android Device

Why do we need to root our device? Because we need to make the OS use a different graphic driver instead from the proprietary one that comes with the device, which means that we need to "modify" OS files or trick the system so that it uses other files, which I'll explain further!

#### Unlocking the Bootloader

Before rooting our device, we need to unlock the bootloader. I won't explain how, since depending on your device the method will differ, and also doing this is not available on all Android devices. It depends on the manufacturer. They need to allow OEM unlocking. In my case, OnePlus is very friendly to bootloader unlocking, so I didn't have any problem.

> [!caution]
> Please, you need to know that unlocking the bootloader will trigger a factory reset (it will wipe all data) and may disable high security apps like banking apps, so do it at your own risk. My recommendation is to not use your daily device for this kind of development.

Without going into details the general steps (which may differ in your case) were these in my case:

- Unlock the Developer Options in your device (if you haven't already).
- In Developer Options on your Android: Enable OEM Unlocking (it's like telling your device "I authorize the bootloader to be unlocked") and USB Debugging (to send commands to the device from your PC).
- Connect your device using a USB to your PC, and in a terminal:
    adb reboot bootloader (to enter into the Bootloader Mode).
- Once in Bootloader Mode, in your terminal type:
    fastboot flashing unlock // On your device, a message confirmation for unlocking the bootloader will pop up -> confirm it.

Now that we have our device with the bootloader unlocked, we can root our device :D

#### Magisk

The easiest and the most common way to root an Android device at the moment that I'm writing this.....is Magisk. 

> [!note] Magisk
> In short, it is a systemless tool. This means that it doesn't need to override the original OS files to make changes, by creating an overlay file system. This is very helpful since if we push some change that produces an error or crash, it won't break our OS. We can just switch back to whatever state we had before.

https://github.com/topjohnwu/Magisk

In my case, these were the steps that I followed to install Magisk:

1. Search for and download the OTA file specific to your device, version, and region.

- To find the version: Settings -> About Device -> Version -> Here you will find the build number.
- To find the region: At the end of the build number, you will see one of of these -> EU/GLO/NA/IN.

> [!note] OTA
> It's just the official software update for your device. Depending on the manufaturer, you will have to find it on their website. Inside, it contains all the files needed for updating your device. This includes init_boost.img (the one we need), boot.img (contains the Linux kernel), system.img (the actual Android OS), etc. 

> [!question]
> Why do we need it? Because Magisk needs to inject its code into the device during the startup process, and that process is inside the file init_boot.img. Since we can't download that file alone, we need to extract it from the OTA. Magisk patches that file, and creates the overlay filesystem that grants the root control.

2. Extract the init_boot.img from the payload.bin inside the OTA, and then send it to your device.

I used this tool to extract it from the payload.bin
https://github.com/ssut/payload-dumper-go

3. Install the Magisk APK from the official repo and select the init_boot.img that you already sent.

In this step, Magisk will add the "root access code" to the init_boot.img and it will repack it into a new file called "magisk_patched.img"

4. Move the file generated by Magisk to your PC and flash your device with it.

```bash
adb reboot bootloader // to get into the Bootloader Mode
fastboot flash init_boot magisk_patched.img
fastboot reboot
```

5. Done :D, check that in the magisk app it says Installed.

FOTO PULGAR ARRIBA CON LA APP

### Configuring Android

Deactivate gaming? how. Max  refresh rae, setting battery max, etc.

## Installing Turnip on your Android Device

We are almost there! For having Turnip running on our device, we need to 2 more things: build Turnip and ship it in a Magisk module to our device.

> [!note] Magisk Modules
> Like we already know, Magisk allows us to give root access to apps and also to make systemless modifications. Those systemless modifications are done through modules. In this case, we'll pack our Turnip .so file into a Magisk module to make the OS use it instead of the proprietary one.

### Building and Injecting Turnip

Since we plan to contribute to the Turnip project, obviously we need to learn how to build it! I won't get into much details, since there are already tutorials explaining this, and I don't see the point of repeating something that is perfectly explained e.e, but I'll write an overview of what you need to do and also share the resources/tutorial that helped me.

It's important to notice that I'm using Ubuntu for this, so the steps may differ from yours!

#### Prerequisites

- Download Mesa... duh!.
- Download the Android NDK (the latest, it doesn't have to match the Android version of your device, as that will be adjusted during the building).
- Install all the library dependencies specified in the tutorials attached below.

> [!note] Android NDK
> The NDK is basically a toolset that allows us to implement parts of Android applications using native code languages like C, C++, and Rust, and also gives us tools for cross-compilation.

Why is it helpful in this case? Well, Turnip belongs to Mesa, and Mesa is written in C and C++ mostly, which means that we need the NDK to compile that C/C++ code into a .so file (libvulkan_mesa.so).

Why a .so file? Because you are probably building the Turnip driver on a x86_64 PC and your Android device uses an ARM64 processor. This means a different architecture, so you need to translate that C/C++ code into instructions that the ARM processor and the Adreno GPU can actually execute.

https://developer.android.com/ndk/downloads

#### Steps

Already having all the prerequisites, these are the steps for building it. If you need more details, please see the links attached below in [[Resources]].

- Create a Meson cross-file: this file tells Meson where your NDK is located and what tools to use instead of the Linux ones.
- Generate the build environment: here you specify what driver to build, the cross-file location, etc, and the makefile.
- Compile the driver: Here I used ninja to execute the compilation by specifying the build directory to search for instructions (the makefiles).
- Inject Turnip into your Android divice using Magisk Modules; The scrip is in the link resources.

Voila! Now, straight out of the oven, we have our delicious Turnip driver (libvulkan_mesa.so) ready for use :)

FOTO DE OVEN

#### Resources

-  İlhan Atahan  - Script for building turnip driver as a magisk module from mesa repository.https://github.com/ilhan-athn7/freedreno_turnip-CI
-  Shankar Vallabhan - Script for building Freedreno Turnip Vulkan Driver as a Module for Magisk or Emulators. https://github.com/v3kt0r-87/Mesa-Turnip-Builder?tab=readme-ov-file
- Lucas Fryzek - Freedreno on Android https://www.youtube.com/watch?v=BrAptxshgPc




! Specify that in driver development you have 2 options mapping of functionality
