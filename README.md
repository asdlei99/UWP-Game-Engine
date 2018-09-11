# Working
I am working to change this to a normal desktop real time rendering framework with DirectX 12. Deferred rendering pipeline will be used.  

# UWPMiniEngine
Mini DirectX game engine for Windows 10 UWP platform  

The UWPMiniEngine is a simple graphic framework which runs on the latest Windows 10 UWP platform. It is written with C++/CX and divided into different individual modules. UWPMiniEngine doesn’t use the Effect framework. It owns a simple method to manage all the HLSL shades and do interaction between CPU and GPU. Currently, it supports the basic render pipeline and several advanced graphic techniques.  

Features:  
1.Dynamic cube mapping  
2.Environment reflection  
3.Billboard tree  
4.Normal and displacement mapping  
5.Adaptive tessellation  
6.Terrain rendering  
7.GPU particle system  
8.GPU wave simulation  
9.Dynamic shadow mapping  
10.SSAO  
11.Efficient custom mesh file format .x3d  
12.High dpi support  
13.MSAA x2/x4/x8 support  
14.Skinned animation  

Organization:  
1.Common: basic modules for the whole engine. Most files can be reused without any modification.   
2.Components: different rendering objects for the UWPMiniEngine including: basic geometry object, particle system, billboard tree, GPU wave, sky, mesh object and terrain. Some helper classes also in this folder such as dynamic cube helper, shadow helper, SSAO helper and loader for x3d file.  
3.Content: samples of the UWPMiniEngine. Each class is a unique rendering scene. You can create one scene in “DXFrameworkMain.cpp” file which manages the rendering pipeline.   
4.Media: all resources for the mini engine including textures, meshes and other models.  
5.Shaders: all the HLSL shaders for different components. Because we don’t use the Effect framework, so vs, ps, cs, gs, hs and ds are in individual files.  
6.X3dConverter: convert fbx file format into x3d file format for rendering with this mini engine. Static meshes and skinned meshes are both supported now.  

Requirements:  
1.Windows 10 OS  
2.Visual Studio 2015  

Notes:  
1.Do config each HLSL shader's type in Visual Studio manually in order to compile these shaders.  
2.For each x3d mesh file, configure it as content in the property menu. Or that Visual Studio cannot recognize these files.  
3.“DXFrameworkMain.cpp” file is very important. It contains all the pipelines for the UWPMiniEngine. So you only need to see this file to figure out how to use this mini engine. Really simple.  
4.Use W/A/S/D to control the camera movement. Use left button to control the camera direction.  
5.Refer to "DeviceResource.cpp" to see configuration of MSAA, high dpi and waitable DXGI swapchain.  
6.The UWPMiniEngine is based on the book <<Introduction to 3D Game Programming with Direct11>>. Thanks to Frank D. Luna.  
7.We pack the necessary data from fbx file into x3d file. FBX SDK is required to do the convertion jod. See "x3dConverter" folder for details.  
8.If you are interested in this project, please contact jxworkcn@yahoo.com.
