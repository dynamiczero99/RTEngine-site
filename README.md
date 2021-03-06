## Rootin' Tootin Engine

Rootin' Tootin' Engine (RTEngine) is a 3D game engine coded in C++ using OpenGL. It is the product of the Game Engines subject in the Bachelor's Degree in Videogame Design and Development. The engine features a scripting system using Lua.

### Developers

![Lorién Portella](https://i.imgur.com/LkIFbxJ.jpg)

**Lorién Portella** ([LinkedIn](https://www.linkedin.com/in/lorien-portella-2144b2159/))

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

**Joel Cabaco** ([LinkedIn](https://www.linkedin.com/in/joel-cabaco-6074a8160/))

- Editor Configuration window (settings for application, camera, render, space partitioning, window, hardware and geometry).
- Primitive creation through par_shapes.
- Time management (play, pause, stop and component updates).
- Asset explorer window.
- Space partitioning (quadtree).
- FPS limitation and management.
- Hardware display.
- Frustum culling.
- Text editor.

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

- Creating Scripts: Scripts can be created or added in both ways. The user can select New Script and input a name (which can not have any blank spaces), or select an already existing script from the Assets//Scripts folder. External scripts can also be used, by placing them in the Assets//Scripts folder but at the moment, the scripting system is very limited, and ony accepts scripts with the TEMPLATE format
- TEMPLATE format: Created to imitate the class system of C, the script needs to be encapsulated in a function with its own name, that returns a table. Inside this table, there needs to be all the script funcionality.
- C++/LUA functions: Easy to expand, right now the engine has three namespaces: BASIC, INPUT, OUTPUT, with a limited API, displayed in the Tank scene, that acts as a demo. 
- BASIC:
- LUALog to log strings into the console
- LUAGetDT to get the dt of the frame in seconds
- DeleteThis to delete the gameobject attached to the script
- INPUT: 
- LUAGetKeyState to get the state of a key
- LUAGetButtonState to get the state of a button
- LUAGetMouseX/Y to get the position of the mouse onscreen
- LUAGetPositionX/Y/Z to get the value from the transform
- OUTPUT: 
- MoveX/Y/Z to move along those axis in global space
- MoveForward to move in the foward vector of the gameobject
- MoveSideways to move perpendicular to the forward of the gameobject
- RotateAlongY to rotate using the Y axis in world space
- Instantiate to instantiate a prefab by name
        
- Tank Scene: Control the tank with WASD. Shoot bullets with the mouse left click. To rotate the turret, move the mouse in the X axis of the screen.

### Demonstration

<iframe width="560" height="315" src="https://www.youtube.com/embed/1WiQMQFruEc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Download

You can check out all of our code in our [Github repo](https://github.com/RootinTootinCoodin/RTEngine), and/or download our [latest release](https://github.com/RootinTootinCoodin/RTEngine/releases/tag/3.0).

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
