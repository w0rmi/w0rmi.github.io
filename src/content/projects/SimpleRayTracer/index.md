---
title: Simple RayTracer
description: Simple RayTracer made with C++17 and GLM.
date: 2022-07-25
categories:
  - ComputerGraphics
  - C++
  - GLM
repositoryUrl:
projectUrl: https://github.com/w0rmi/SimpleRayTracer
status: completed
image: "[[https://user-images.githubusercontent.com/19228971/178521019-93b74f3e-f9ea-4de8-8e49-68aa15a88aa8.jpeg]]"
hideCoverImage: false
hideTOC: false
draft: false
featured: true
aliases:
  - project-simpleRayTracer
---
## Project Overview

This is my implementation of a simple RayTracer. There is a lot of space for more features but the purpose of this project was to make my first steps in a RayTracer and to leave a base-template to create a more comple one in the future.

## Features

- **Movable Camera.**
- **MSAA(Multisampling Antialiasing).**
- **Materials: Dielectric, Diffuse and Metal.**
- **Surface: Sphere.**
- **Depth of Field.**
- **Output file format: PPM.**
- **All the parameters of the features can be changed in the config.h file.**

## Preview of the Features

- **Movable Camera**
![alt](https://user-images.githubusercontent.com/19228971/178526657-7a8f36e8-47e5-48ac-bb3c-70085567cc22.jpeg)

- **MSAA**
![alt](https://user-images.githubusercontent.com/19228971/178537351-26489eae-07d8-486e-9ded-70e9663f69c3.jpeg)
Left image without MSAA - Right image with MSAA(# of samples = 100)

- **Diffuse Material**
![alt](https://user-images.githubusercontent.com/19228971/178542458-39290277-57ec-4633-9a4b-ef6368aa3cb2.jpeg)

- **Dielectric Material**
![alt](https://user-images.githubusercontent.com/19228971/178546408-6565aeec-e131-47d8-9737-2ff8f055c6a0.jpeg)

- **Metal Material**
![alt](https://user-images.githubusercontent.com/19228971/178548651-a94f43b9-ce79-440f-bdd3-763ce231b34e.jpeg)

- **DoF**
![alt](https://user-images.githubusercontent.com/19228971/178552159-6fc79557-7134-4e47-aefb-be04c6b7c163.jpeg)
VFO: 30, ApertureSize: 0.3

## Environment

- **Linux.**
- **C++17**
- **GLM**

## Prerequisites

- **g++**
- **CMake >= 3.9.1**

## Documentation

- **[https://raytracing.github.io/books/RayTracingInOneWeekend.html](https://raytracing.github.io/books/RayTracingInOneWeekend.html)**
- **[https://viclw17.github.io/writing.html](https://viclw17.github.io/writing.html)**

## How to run it

```
$ git clone https://github.com/SaferGo/Simple-Ray-Tracer.git
$ cd Simple-Ray-Tracer
$ bash run.sh
You can find the img file in the output folder.
```

<a href="https://github.com/w0rmi/SimpleRayTracer" class="no-styling no-underline" target="_blank"><button class="btn btn-primary w-full">  
    View Project  
  </button></a>
