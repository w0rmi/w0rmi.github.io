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
![alt](https://user-images.githubusercontent.com/19228971/208724316-87dfa63a-009f-4d35-baeb-b79d53ebc0b4.png)
![alt](https://user-images.githubusercontent.com/19228971/209079610-2f5d3d81-85b4-43af-8cb9-ee51745c7f61.png)
![alt](https://user-images.githubusercontent.com/19228971/209082602-83f74c8c-82e8-473e-ab07-cc3728794cad.png)
![alt](https://user-images.githubusercontent.com/19228971/209096509-659410ea-839a-4508-a0bd-b3f551afb9a8.png)
![alt](https://user-images.githubusercontent.com/19228971/220130551-4b028896-ffc6-4489-898e-e9c5822541ec.png)
---

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

- **ASSIMP**: Mesh and material loading.
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

```C++
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

## Technical Implementation

Built with TypeScript and following Obsidian's plugin development best practices, the plugin integrates seamlessly with Obsidian's file system and provides a smooth user experience for content creators. It supports both file-based (`my-post.md`) and folder-based (`my-post/index.md`) post structures, making it flexible for different Astro setups.

## Installation

Astro Composer is not yet available in the Community plugins section. Install using BRAT or manually:

### BRAT (Recommended)
1. Download the Beta Reviewers Auto-update Tester (BRAT) plugin from the Obsidian community plugins directory and enable it
2. In the BRAT plugin settings, select `Add beta plugin`
3. Paste: `https://github.com/davidvkimball/obsidian-astro-composer` and select `Add plugin`

### Manual Installation
1. Download the latest release from the Releases page
2. Navigate to your Obsidian vault's `.obsidian/plugins/` directory
3. Create a new folder called `astro-composer` and ensure `manifest.json`, `main.js`, and `styles.css` are in there
4. In Obsidian, go to Settings > Community plugins and enable "Astro Composer"

## Usage

1. **Customize Settings**: In **Settings > Astro Composer**, configure automation, properties template, posts folder, creation mode, and more
2. **Standardize Properties**: Use the `Astro Composer: Standardize Properties` command to update a note's properties to the relevant content type
3. **Convert Internal Links**: Use the `Astro Composer: Convert internal links for Astro` command to transform Obsidian wikilinks and internal Markdown links into Astro-compatible Markdown links
4. **Rename Content**: Using the `Astro Composer: Rename Current Note` command, set the title of your content and have the file or parent folder get automatically renamed with the kebab-case version

## Use Cases

- **Content Creators**: Streamline the process of creating and managing blog posts, pages, and documentation
- **Astro Developers**: Bridge the gap between Obsidian note-taking and Astro publishing
- **Technical Writers**: Maintain consistent formatting and file organization across multiple content types
- **Bloggers**: Focus on content creation rather than file management and slug generation
- **Vault CMS Users**: Core automation component for the complete Obsidian-to-Astro workflow

## Project Status

This project is actively maintained and in-progress. The latest version includes robust automation features, comprehensive configuration options for various Astro workflows, and support for multiple content types beyond just posts.

<a href="https://github.com/davidvkimball/obsidian-astro-composer" class="no-styling no-underline" target="_blank"><button class="btn btn-primary w-full">  
    View Project  
  </button></a>
