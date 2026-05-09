---
title: "My Turnip Merge Quest: Setup, Device, and Build"
category: "MyTurnipMergeQuest"
date: 2026-01-04
order: 3
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
<center>

# Leaving the Shire

![alt](https://images.unsplash.com/photo-1738998725908-43c8ab741913?q=80&w=1331&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [DJ](https://unsplash.com/@djthoms) - [Unsplash](https://unsplash.com/)*

Probably this post will be long, so have patience with it e.e. My plan for this post is to **share my setup and help you to leave everything ready to develop comfortably on** [Turnip](posts/myturnipmergequest0#goal), and this also means connecting with other developers/communities that will help us through this journey (by gathering info and help), how to configure and leave the hardware prepared for development, and also how to set up Turnip. 

</center>

> [!caution]
> My objective for this series is to document my own journey in hopes that it might help others along the way. This is not a tutorial/manual on the 'best' way to do things. It's just my personal experience. I hope it helps you find your own path :)

---

## Communication

![alt](https://images.unsplash.com/photo-1568258805731-c117485e50c2?q=80&w=772&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Sandra Tan](https://unsplash.com/@sandratansh) - [Unsplash](https://unsplash.com/)*

First things first, **we need to connect with the people working on the project** obviously! I think one important aspect of working on an OSS project is to get involved and participate, so that's what we'll try to do.
These are the communications means that I found, but please if you know any other, share it with me and I'll update the list.

### IRC

I won't get into details since there are a lot of better tutorials for that. But, basically it's a **text only chat**, where you need an IRC client to connect to any network. In my case, I use [Halloy](https://halloy.chat/), which works great.

![[halloy.png]]
*Halloy*


The server and channels used by or relevant to the Turnip developers are:

| Server    | irc.oftc.net           |
| --------- | ---------------------- |
| Channels  | freedreno && dri-devel |

To find old chats, you can check this website:

https://dri.freedesktop.org/~cbrill/dri-log/index.php

Also, there is an [app](https://play.google.com/store/apps/details?id=de.egore911.drilog&hl=en_GB) that you can install on your Android device.

### Mailing List

![alt](https://images.unsplash.com/photo-1578655083045-1974aed129e6?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Leksandr Gamaniuk](https://unsplash.com/@oleksander_gamaniuk) - [Unsplash](https://unsplash.com/)*

It's a **subscription mailing list** in which you can ask and answer questions. The discussions will be received weekly(?) by all the the developers subscribed. I think it's relevant to know the latest discussions and also to ask for help if needed.

More info here:

https://docs.mesa3d.org/lists.html

To find old messages, you can check this website:

https://lists.freedesktop.org/archives/mesa-dev/

---

## Learning Resources

Here are the resources that I found related to Turnip that will help us along the way:

### Official Documentation and Code

![alt](https://images.unsplash.com/photo-1587716283570-f71969a1f854?q=80&w=1465&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [David Nitschke](https://unsplash.com/@david_nitschke_95) - [Unsplash](https://unsplash.com/)*

Obviously the most important documentation is the official one. Sadly, it has some outdated information, but it is nevertheless still very relevant.

https://docs.mesa3d.org/drivers/freedreno.html

### Tutorials

These were the ones that I could find:

- `Danylo Piliaiev Tutorials`


https://blogs.igalia.com/dpiliaiev/turnips-in-the-wild-part-1/


Extremely helpful and also they are made by one of the main developers of Turnip. In their blog, they share info on how to debug Turnip.

- `Lucas Francisco Fryzek Tutorials`


https://fryzekconcepts.com/index.html


Same, very helpful tutorials, in this case made and shared by Lucas, another important developer from [Igalia](https://www.igalia.com/). 


### Conference Speeches

As I already shared on this [post](/posts/myturnipmergequest1#oss-conferences), there are several conferences related to the graphic stack. Those talks will help us a lot along the way. Please refer to my old post to find out more.

---
## Preparing the Android Device for Turnip

![alt](https://images.unsplash.com/photo-1771366629891-9db2a25481f6?q=80&w=1744&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Calvin Wise](https://unsplash.com/@wiseboysca) - [Unsplash](https://unsplash.com/)*

You have two options for using Turnip on Android: **either you use it internally through an emulator, or you use the driver in the whole OS**. The latter option is better since debugging through an emulator would be painful.

Changing the graphic driver in our Android OS is not so easy as in Linux, but neither it is too hard (for now...). I'll share what I did to leave my tablet ready for using Turnip.

### Rooting the Android Device

![alt](https://images.unsplash.com/photo-1592921195496-6ff2e332c0f6?q=80&w=2062&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Vanna Phon](https://unsplash.com/@phonvanna) - [Unsplash](https://unsplash.com/)*

**We need to root our device to make the OS use a different graphic driver instead from the proprietary one** that comes with the device, which means that we need to "modify" OS files or trick the system so that it uses other files, which I'll explain further.

#### Unlocking the Bootloader

**Before rooting our device, we need to unlock the bootloader**. I can't explain the process specifically, since depending on your device the method will differ, and also doing this is not possible on all Android devices. It depends on the manufacturer. They need to allow OEM unlocking. In my case, OnePlus is very friendly to bootloader unlocking, so I didn't have any problem. So, I'll explain what I did.

> [!caution]
> Please, you need to know that unlocking the bootloader will trigger a factory reset (it will wipe all data) and may disable high security apps like banking apps, so do it at your own risk. My recommendation is to not use your daily device for this kind of development.

Without going into details the general steps (which may differ in your case) were these:

1. Unlock the Developer Options in your device (if you haven't already).
2. In Developer Options on your Android: Enable OEM Unlocking (it's like telling your device "I authorize the bootloader to be unlocked") and USB Debugging (to send commands to the device from your PC).
3. Connect your device using a USB to your PC, and in a terminal:
```bash
    adb reboot bootloader // to enter into the Bootloader Mode
```
4. Once in Bootloader Mode, in your terminal type:

```bash
fastboot flashing unlock // On your device, a message confirmation for unlocking the bootloader will pop up -> confirm it.
```

==Now that we have our device with the bootloader unlocked, we can root our device :D==

#### Magisk

The easiest and the most common way to root an Android device at the moment that I'm writing this.....is [Magisk](https://github.com/topjohnwu/Magisk).

> [!note] Magisk
> In short, it is a systemless tool. This means that it doesn't need to override the original OS files to make changes, by creating an overlay file system. This is very helpful since if we push some change that produces an error or crash, it won't break our OS. We can just switch back to whatever state we had before.

https://github.com/topjohnwu/Magisk

In my case, these were the steps that I followed to install Magisk:

1. Search for and download the OTA file specific to your device, version, and region.

    - **To find the version**: Settings -> About Device -> Version -> Here you will find the build number.
    - **To find the region**: At the end of the build number, you will see one of of these -> EU/GLO/NA/IN.

> [!note] OTA
> It's just the official software update for your device. Depending on the manufaturer, you will have to find it on their website. Inside, it contains all the files needed for updating your device. This includes init_boost.img (the one we need), boot.img (contains the Linux kernel), system.img (the actual Android OS), etc. 

> [!question] Why do we need the OTA file?
> Because Magisk needs to inject its code into the device during the startup process, and that process is inside the file init_boot.img. Since we can't download that file alone, we need to extract it from the OTA. Magisk patches that file, and creates the overlay filesystem that grants the root control.

2. Extract the init_boot.img from the payload.bin inside the OTA, and then send it to your device.

    - I used this tool to extract it from the payload.bin:

https://github.com/ssut/payload-dumper-go

3. Install the Magisk APK from the [official repo](https://github.com/topjohnwu/Magisk) and select the init_boot.img that you already sent.

    - In this step, Magisk will add the "root access code" to the init_boot.img and it will repack it into a new file called "magisk_patched.img"

4. Move the file generated by Magisk to your PC and flash your device with it.

    ```bash
    adb reboot bootloader // to get into the Bootloader Mode
    fastboot flash init_boot magisk_patched.img
    fastboot reboot
    ```

5. Done :D, check that in the magisk app it says *Installed*.

![[magisk.jpg]]
*Image from [w0rmi](https://w0rmi.github.io/about/)*

### Configuring Android

![alt](https://images.unsplash.com/photo-1685062428479-e310b7851de5?q=80&w=1480&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Mohamed Nohassi](https://unsplash.com/@coopery) - [Unsplash](https://unsplash.com/)*

Depending on your manufacture and your Android OS version, **you probably have different settings that may limit your device because of the battery usage**. For example, your device might not be using the highest performance possible, or it may be limiting the refresh rate, etc. 

**While debugging or testing, we need to use our device at its maximum capacity**. To do that, we need to activate or deactivate some settings. I didn't find much information regarding this, but I assumed that it's better to have everything unlocked, so here I share what I did. Also, I want to share some very helpful apps for debugging.

#### Maximizing Hardware Performance

These were the settings I changed:

- **Refresh Rate**: Activate the max option in the settings.
- **Battery Mode**: Change it to use the "High Performance Mode" in the settings.
- **RAM Expansion**: Deactivate it to use just the physicall RAM. Using the virtual one may produce issues with Turnip.

#### Helpful Apps

- [Vulkan Caps Viewer](https://play.google.com/store/apps/details?id=de.saschawillems.vulkancapsviewer&hl=en_GB): This is a very helpful app that tells use everything about our Vulkan driver, such as available extensions, apiVersion, driver version, etc.
- [MiXplorer](https://mixplorer.com/#intro): You can use this one or any other Android file explorer (that supports root access). We'll use it in the future to navigate though OS files that you can only be accessed with root permissions.
- [Termux](https://play.google.com/store/apps/details?id=com.termux&hl=en_GB): It's a terminal emulator for Android.
- Magisk: Already explained.

For starting, these are enough. In the next post, I'll share some more tools that we'll use for debbuging (e.g gfxrecon-replay, winlator, etc) and explain how to install and use them.

---

## Installing Turnip on your Android Device

We are almost there! To get Turnip running on our device, we need to do 2 more things: **build Turnip and ship it to our device via a Magisk module.**

> [!note] Magisk Modules
> As we already know, Magisk allows us to give root access to apps and make systemless modifications. These systemless modifications are done through modules. In this case, we'll pack our Turnip .so file into a Magisk module to force the OS to use it instead of the proprietary driver.

### Building and Injecting Turnip

![alt](https://images.unsplash.com/photo-1615134680505-30e8b8c07953?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Tracey Parish](https://unsplash.com/@tip_to) - [Unsplash](https://unsplash.com/)*

Since we plan to work with Turnip, obviously we need to learn how to build it! There are already tutorials and scripts of how to do this, so I won't get into much details. I don't see the point of repeating something that is perfectly explained e.e. However, I'll write an overview of what you need to do and also share the [resources](/posts/myturnipmergequest3#resources) that helped me.

> [!caution]
> It's important to notice that I'm using Ubuntu for this, so the steps may differ from yours!

#### Prerequisites

- Download Mesa... duh!
- Download the Android [NDK](https://developer.android.com/ndk/downloads): Use the latest, it doesn't have to match the Android version of your device, as that will be adjusted during the building process.

> [!note] Android NDK
> The NDK is basically a toolset that allows us to implement parts of Android applications using native code languages like C, C++, and Rust, and also gives us tools for cross-compilation.

> [!question] Why do we need NDK?
> Well, Turnip belongs to Mesa, and Mesa is written in C and C++ mostly, which means that we need the NDK to compile that C/C++ code into a .so file (libvulkan_mesa.so).

> [!question] Why a .so file?
> Because you are likely building the Turnip driver on a x86_64 PC, but your Android device uses an ARM64 processor (probably). Because there are different architectures, you need to translate that C/C++ code into instructions that the ARM processor can actually execute.

- Install all the library dependencies: Make sure to install all the dependencies specified in the links attached below.


#### Steps

Already having all the prerequisites, these are the steps for building it. If you need more details, please see the links attached in the [resources](/posts/myturnipmergequest3#resources) section.

- **Create a Meson cross-file**: This file tells Meson where your NDK is located and which tools to use instead of the Linux standard ones.
- **Generate the build environment**: Here you specify which driver to build, the cross-file location, and generate the build files.
- **Compile the driver**: I used ninja to execute the compilation by specifying the build directory to search for instructions (the makefiles).
- **Inject Turnip into your Android device**: Pack the driver in a Magisk Module and then ship it to the Android device.
- **Activate the module in the Magisk app**: The device will reboot, and Turnip will be set as the primary graphic driver.

==Voila! Now, straight out of the oven, we have our delicious Turnip driver ready for use :)==

![alt](https://images.unsplash.com/photo-1693307090398-2a6d5cc39c77?q=80&w=774&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
*Image from [Anna Ansone](https://unsplash.com/@simplyanna) - [Unsplash](https://unsplash.com/)*

If everything is correct, you should see in the [Vulkan Hardware Capability Viewer App](posts/myturnipmergequest3####Apps) that it says Turnip :D

![[HardwareApp.jpg]]
*Image from [w0rmi](https://w0rmi.github.io/about/)*

---

### Resources

-  **İlhan Atahan**  - Script for building turnip driver as a magisk module from mesa repository.

https://github.com/ilhan-athn7/freedreno_turnip-CI

-  **Shankar Vallabhan** - Script for building Freedreno Turnip Vulkan Driver as a Module for Magisk or Emulators.

https://github.com/v3kt0r-87/Mesa-Turnip-Builder?tab=readme-ov-file


- **Lucas Fryzek** - Freedreno on Android.


https://www.youtube.com/watch?v=BrAptxshgPc


