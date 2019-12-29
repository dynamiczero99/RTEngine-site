## Rootin' Tootin Engine

Rootin' Tootin' Engine (RTEngine) is a 3D game engine coded in C++ using OpenGL. It is the product of the Game Engines subject in the Bachelor's Degree in Videogame Design and Development. The engine features a scripting system using Lua.

### Developers

![Lorién Portella](https://i.imgur.com/LkIFbxJ.jpg)

Lorién Portella ([LinkedIn](https://www.linkedin.com/in/lorien-portella-2144b2159/))

- Model importing.
- Model rendering.
- Own file format.
- Hierarchy.
- Tri-based mouse picking.
- Inspector.
- Console.
- Texturing.
- Gameobject and component structure.
- Serialization.
- Scripting system.

![Joel Cabaco](https://i.imgur.com/VFvuzGz.jpg)

Joel Cabaco ([LinkedIn](https://www.linkedin.com/in/joel-cabaco-6074a8160/))

- Editor Configuration window (settings for application, camera, render, space partitioning, window, hardware and geometry).
- Primitive creation through par_shapes.
- Time management (play, pause, stop and component updates).
- Asset explorer window.
- Space partitioning (quadtree).
- FPS limitation and management.
- Hardware display.
- Frustum culling.
- Text editor.

``TODO: Add all contributions``

### Core subsystems

#### OpenGL

Our engine is able to load and display models through OpenGL. These models are drawn using buffers created from the vertex data on the loaded files. It supports drag and drop for loading. These models can also be textured, either with a checkered texture given by the own engine, or by any texture loaded into it.

#### UI and respective subsystems

RTEngine uses the ImGui library for its UI. We feature many windows in order to manage and keep track of different elements of the engine:

- **Scene**: This is the 3D OpenGL environment where the models are loaded and used.

- **Configuration**: This window displays the status for the main settings of the engine. The application submenu displays the FPS and last frame ms, enables the limiting of FPS, and changes the name of the window or the organization. The editor camera submenu has the options for camera movement in the editor and can enable or disable the debug draw of the camera frustum and the frustum culling. In the render submenu are the options for the different OpenGL renderer settings such as face culling, lighting, depth test, etc, and also contains the display options for the scene axis and grid. The space partitioning submenu includes the debug draw for the quadtree and the bucket for each quadtree node. The window submenu has the options for the program window such as width, height, brightness, the refresh rate of the monitor the window is currently in, fullsceen toggle, etc. The hardware submenu simply displays the SDL version and the specifications of the PC the engine is currently running on. Finally, in the geometry submenu different primitives can be created into the scene, selecting the number of slices and stacks of the generated item.

- **Hierarchy**: In the hierarchy the different gameobjects can be seen, selected and nested. The scene can also be saved in this window.

- **Inspector**: The inspector shows data for the current gameobject's components as well as its transform and texture, its UUID, and other important data.

- **Time**: The time window allows playing, pausing and stopping of the scene in-game clock, in order to test scripts in real time.

- **Assets**: The assets window shows an explorer in order to select resources to be imported to the engine such as models, textures or scripts.

- **Console**: The console shows logs giving information of the engine's processes such as prompts when loading a new mesh with info on the number of vertices and indices or the state of loading configuration files.

- **About**: The about window shows the different libraries used with version number and (if appliable) the home site of said library.

### Main subsystem: scripting

### Demonstration

### Download

You can check out all of our code in our [Github repo](https://github.com/RootinTootinCoodin/RTEngine), and/or download our [latest release](https://github.com/RootinTootinCoodin/RTEngine). ``Todo: change release link to actual release).``

### License

MIT License

Copyright (c) 2019 RootinTootinCoodin (Joel Cabaco and Lorién Portella)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
