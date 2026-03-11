---
title: Croissant - Real-Time Vulkan Renderer
description: Real-time vulkan renderer with features like PBR, IBL and more.
date: 2023-03-02
categories:
  - Obsidian
  - Astro
  - Plugin
repositoryUrl:
projectUrl: https://github.com/w0rmi/CroissantVulkanRenderer
status: in-progress
image: "[[attachments/rock.png]]"
imageAlt: Gray, rocky wall
hideCoverImage: false
hideTOC: false
draft: false
featured: true
aliases:
  - obsidian-astro-composer
---
## About

The aim of this project was to create a properly functioning render graph that would allow me to learn and experiment with Vulkan, as well as provide an opportunity to learn graphics techniques.

## Render Samples

![alt](https://user-images.githubusercontent.com/19228971/208722571-807d33d1-5da5-4118-9529-bf0ed000291f.png)

---
s
![alt](https://user-images.githubusercontent.com/19228971/208724316-87dfa63a-009f-4d35-baeb-b79d53ebc0b4.png)
![alt](https://user-images.githubusercontent.com/19228971/209079610-2f5d3d81-85b4-43af-8cb9-ee51745c7f61.png)
![alt](https://user-images.githubusercontent.com/19228971/209082602-83f74c8c-82e8-473e-ab07-cc3728794cad.png)
![alt](https://user-images.githubusercontent.com/19228971/209096509-659410ea-839a-4508-a0bd-b3f551afb9a8.png)
![alt](https://user-images.githubusercontent.com/19228971/220130551-4b028896-ffc6-4489-898e-e9c5822541ec.png)

## Features

- **Physically based rendering(Cook–Torrance BRDF).**
- **Image based lighting.**
- **Forward rendering.**
- **Multisample anti-aliasing (MSAA).**
- **HDRI skymap loading.**
- **Compute shaders.**
- **Shadow mapping.**
- **Normal mapping.**
- **Different light types (directional, point and spot lights).**
- **Texture mipmaps.**
- **Arcball camera.**
- **GUI.**

### Other Features

- **Multi-threaded texture asset importing.**
- **Model loading.**


## Code Structure

```
Croissant
|
|-- assets              
|   |-- models              # Meshes and textures
|   `-- skybox              # HDR files with their generated irradiance, prefiltered env. and BRDFlut textures
|
|-- bin                     # Contains the executable files
|
|-- build                   # CMake compile
|
|-- include                 # Project header files
|   `-- Settings            # All user tweakable settings files(scene, camera, pipeline, etc)
|
|-- libs                    # Dependencies
|   |-- ASSIMP
|   |-- GLFW
|   |-- GLI
|   |-- GLM
|   |-- Dear imgui           
|   |-- stb_image
|   |-- tracy
|   |-- Vulkan-Loader            
|   `-- Vulkan-Tools
|
|-- shaders
|
|-- src                     # C++ implementation files
|   |-- Buffer
|   |-- Camera
|   |-- Command
|   |-- Computation
|   |-- Descriptor
|   |-- Device
|   |-- Features
|   |-- Framebuffer
|   |-- GUI
|   |-- Image
|   |-- Math
|   |-- Model
|   |-- Pipeline
|   |-- Queue
|   |-- Renderer
|   |-- RenderPass
|   |-- Scene
|   |-- Shader
|   |-- Swapchain
|   |-- Texture
|   |-- VkInstance
|   `-- Window
|   
`-- CMakeLists.txt          # CMake build script
```


## Third Party Libraries

Here's the list of the libraries included in the project:

- **[ASSIMP](https://github.com/assimp/assimp)**: Mesh and material loading.
- **GLFW**: A multi-platform library for window and input.
- **GLI**: Image library(used to generate the BRDFlut texture).
- **GLM**: Mathematics library fro graphics software.
- **ImGui**: GUI.
- **stb_image**: Image encoding/decoding.
- **Tracy**: Frame profiler.
- **Vulkan-Loader**
- **Vulkan-Tools**: Validation Layers.

## Render Graph

![alt](https://user-images.githubusercontent.com/19228971/209051311-cfe64c87-710d-4b91-aeb9-86c881e39406.png)

![alt](https://user-images.githubusercontent.com/19228971/209051351-86eb79c7-b32f-44f4-b185-132790dc7297.png)


## Usage

```cpp
/* Commands:
*   
*   - addSkybox(fileName, folderName);
*   - addObjectPBR(name, folderName, fileName, position, rotation, size);
*   - addDirectionalLight(name, folderName, fileName, color, position, targetPosition, size);
*   - addSpotLight(name, folderName, fileName, color, position, targetPosition, rotation, size);
*   - addPointLight(name, folderName, fileName, color, position, size);
*
*   - demo1(); // Damaged Helmet
*   - demo2(); // AK 47
*   - demo3(); // Collier Flintlock Revolver
*   - demo4(); // Sponza day
*   - demo5(); // Sponza night
*   - demo6(); // Metal Rough Spheres
*/

int main()
{
   Renderer app;

   try
   {
      // Scene
      {
         app.addSkybox("fileName.hdr", "folderName");
         app.addObjectPBR(
               "name",
               "folderName",
               "fileName",
               glm::fvec3(0.0f), // Position
               glm::fvec3(0.0f), // Rotation
               glm::fvec3(1.0f)  // Size
         );
         app.addDirectionalLight(
               "name",
               "folderName",
               "fileName",
               glm::fvec3(1.0f), // Color
               glm::fvec3(0.0f), // Position
               glm::fvec3(1.0f), // Target Position
               glm::fvec3(1.0f)  // Size
         );
      }

      app.run();

   } catch (const std::exception& e)
   {
      std::cerr << e.what() << "\n";

      return 0;
   }

   return 0;
}
```

## Controls

| **Input**    | **Action**     |
| ---------    | ---------      |
| RMB drag     | Rotate Camera  |
| Scroll wheel | Zoom in/out    |

## Dependencies

- ** cmake >= 3.9.1 **
- ** gcc >= 9.4.0 **
- ** vulkan-validationlayers-dev **
- ** spirv-tools **
- ** glslc **

## Building on Linux

```
$ git clone --recurse-submodules https://github.com/SaferGo/CroissantVulkanRenderer.git
$ cd CroissantVulkanRenderer/build
$ bash buildReleaseMode.sh
// or buildDebugMode.sh

```
After a successful build, the resulting executable can be found in the bin directory.

## Tested Toolchains

| **Compiler** |            **Operating System**           | **Architecture** |
| ---------    | ----------------------------------------- | ------------------ |
| GCC 9.4.0    | Linux Ubuntu 20.04.4 with kernel 5.8.0-53 | x64                |

## References

- [Vulkan Tutorial](https://vulkan-tutorial.com/).
- [3D Graphics Rendering Cookbook: A comprehensive guide to exploring rendering algorithms in modern OpenGL and Vulkan.](https://www.amazon.de/dp/1838986197)
- [Vulkan Cookbook: Solutions to next gen 3D graphics API.](https://www.amazon.de/dp/1786468158)
- [Hybrid Rendering Engine by Angelo1211.](https://github.com/Angelo1211/HybridRenderingEngine)
- [Vulkan physically-Based Rendering by SaschaWillems.](https://github.com/SaschaWillems/Vulkan-glTF-PBR)
- [Shadow Mapping in Vulkan by igalia.](https://blogs.igalia.com/itoral/2017/07/30/working-with-lights-and-shadows-part-ii-the-shadow-map/)
- [Integrating Dear ImGui in a custom Vulkan renderer.](https://frguthmann.github.io/posts/vulkan_imgui/)

## Included Assets

The following assets are bundled with the project:

### - HDRs

- Winter Forest and Apartment from [ihdri](https://polyhaven.com/hdris).
- Country Club, Farm Field, Neon Photostudio, Peppermint Powerplant 2 and Shangai Bund from [PolyHaven](https://polyhaven.com/) (distributed under [CC0](https://polyhaven.com/license)).
- Arches PineTree from [HdrLabs](https://hdrlabs.com/)(distributed under [Creative Commons Attribution-Noncommercial-Share Alike 3.0 License](https://creativecommons.org/licenses/by-nc-sa/3.0/us/)).

### - Models

- Cube from [Cesium](https://cesium.com/) (distributed under [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)).
- Damaged Helmet from [theblueturtle_](https://sketchfab.com/theblueturtle_)(distributed under [Creative Commons Attribution-Noncommercial-Share Alike 3.0 License](https://creativecommons.org/licenses/by-nc-sa/3.0/us/)).
- Sponza from [alexandre-pestana](https://www.alexandre-pestana.com/).
- Metal Rough Spheres from Analytical Graphics (distributed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)).
- AK 47 Tactical Upgrade from [Mateusz Woliński](https://sketchfab.com/jeandiz) (distributed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)).
- Collier Flintlock Revolver from [Artem Goyko](https://sketchfab.com/Artem.Goyko) (distributed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)).

<a href="https://github.com/w0rmi/CroissantVulkanRenderer" class="no-styling no-underline" target="_blank"><button class="btn btn-primary w-full">  
    View Project  
  </button></a>
