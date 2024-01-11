---
{"dg-publish":true,"permalink":"/adv/cg-outline/","title":"Tools","noteIcon":""}
---


# Tools

## Common

1. Openpype 开源的管道工具。
2. GeoTracker
3. FaceTracker (KeenTools 系列中的脸部追踪工具)
4. Tiny Eye (制作眼球的工具，支持Blender的Cycles和Eevee)
5. Allusion [Allusion](https://github.com/allusion-app/Allusion) 管理你的图片库。
6. Cascade 基于节点的图片编辑。
7. GimelStudio 基于节点的图片编辑。
8. Krita 绘画软件。
9. cgru 更详细: [[adv/cg_pipeline\|CG Pipeline]] CGRU 是计算机图形工具包。其中Afanasy是一个渲染场管理器。 Rules 是一个CG 项目跟踪器。
10. storyboarder 故事版制作软件。
11. xComp 渲染结果比较工具。 [xComp](https://github.com/gugenstudio/xComp)
12. Mandelbulber v2 可以生成三维分形的软件。
13. MeshLib 用于处理和编辑 3D网格的系统。
14. Wings3D 介绍说是一款对模型进行细分的工具。
15. QuiltiX 基于节点的MaterialX材质编辑。

## Renderer

1. openmoonray - 梦工厂开源的渲染器。
2. Guerilla render - 描述中称在灯光与外观开发方面比较出色的一款渲染器。
3. gatling [gatling](https://github.com/pablode/gatling) - 基于Hydra的光追渲染器。
4. Cycles - Blender中的基于物理的渲染器。
5. kajiya - 实时全局光照渲染器。

## Blender

1. Poly Haven Assets Add-on [polyhavenassets](https://github.com/Poly-Haven/polyhavenassets)
2. VF-BlenderAutosaveRender https://github.com/jeinselen/VF-BlenderAutosaveRender

## awesome 系列

1. [GitHub - cgwire/awesome-cg-vfx-pipeline: List of open-source technologies that help in the process of building a pipeline for CG and VFX productions](https://github.com/cgwire/awesome-cg-vfx-pipeline)
2. [GitHub - agmmnn/awesome-blender: 🪐 A curated list of awesome Blender addons, tools, tutorials; and 3D resources for everyone.](https://github.com/agmmnn/awesome-blender)

# CG Assets

1. https://github.com/knightcrawler25/GLSL-PathTracer assets
2. https://github.com/LuxCoreRender/LoL LuxCoreRender online asset library
3. https://luxcorerender.org/example-scenes/ LuxCoreRender Example Scenes
4. PolyHaven https://polyhaven.com/
5. Quixel Bridge https://quixel.com/bridge
6. AMD GPUOpen MaterialX Library https://matlib.gpuopen.com/main/materials/all
7. Mixamo https://www.mixamo.com/
8. Blender Cloud Libraries https://cloud.blender.org/libraries
	1. Cloud Gallery https://cloud.blender.org/p/gallery/
	2. HDRI https://cloud.blender.org/p/hdri
	3. Textures https://cloud.blender.org/p/textures
	4. Characters https://studio.blender.org/characters/
9. Blender Demo Files https://www.blender.org/download/demo-files/
10. freepoly.org https://www.freepoly.org/en
11. free3d https://free3d.com/3d-models/
12. sketchfab https://sketchfab.com/
13. 3D Scans https://threedscans.com/ - 3D扫描模型

# Houdini

[[adv/houdini_hello\|Houdini Hello]]

# Unity

## 艺术准备

1. 绑定是否满足Unity-Humanoid-Avatar (是 Unity 识别特定动画模型是否为人形布局的方法，以及该模型的腿部、手臂、头部和身体的对应部分。) 的要求
2. 动画的BlendShape满足ARKit命名规范

**Maya**

> ADV

**Unity**

Packages

> Subscenes  
> Cinemachine  
> InputSystem  
> HDRP - Volumetric Cloud 高清渲染管线  
> ML-Agents

Store

> Magic Cloth  
> Dynamic Bone  
> HAIRWORKS  
> Gaia 地形工具  
> Terrain Composer 2 地形工具  
> Obi 基于 CPU 的 Unity 实时粒子物理引擎  
> Playmaker 交互式游戏设计  
> Amplify Shader Editor (Pack) 材质编辑器  
> KWS Water System (HDRP) 用于模拟海洋/大海/河流/湖泊/池塘等水面  
> Polygon Pack  
> Amplify Impostors 使用billboard技术来表示复杂几何。

OpenSource

> [usd-unity-sdk](https://github.com/Unity-Technologies/usd-unity-sdk)  
> [glTFast](https://github.com/atteneder/glTFast)  
> Houdini引擎 Houdini Engine

> Sentis [About Sentis Beta - AI Beta / Sentis - Unity Discussions](https://discussions.unity.com/t/about-sentis-beta/260899/1)

## 制作考虑

动画融合-Mixamo  
Houdini程序化生成（地形，建筑，场景…）  
动作捕捉，面部捕捉

## 工具插件

### Houdini Engine

Install

在编辑器Project->Assets中，Import Package ->Custom Package...，选择到Houdini安装目录(engine/unity/HoudiniEngineUnity.unitypackage) 或者也可以从Github仓库[GitHub - sideeffects/HoudiniEngineForUnity: Houdini Engine for Unity](https://github.com/sideeffects/HoudiniEngineForUnity)安装。

> https://www.sidefx.com/products/houdini-engine/plug-ins/


### USD

Installing

[GitHub - Unity-Technologies/usd-unity-sdk: Integration of Pixar's Universal Scene Description into Unity](https://github.com/Unity-Technologies/usd-unity-sdk)

- installing by name, "com.unity.formats.usd";
- installing by Git URL, "[https://github.com/Unity-Technologies/usd-unity-sdk.git?path=package/com.unity.formats.usd](https://github.com/Unity-Technologies/usd-unity-sdk.git?path=package/com.unity.formats.usd)";
- or browsing for a local package with path `<root>/package/com.unity.formats.usd/package.json.`

## 工具集合

1. Unity Live Capture [[adv/unity_live_capture\|Unity Live Capture]]

## 开源仓库

### Tools

[GitHub - Unity-Technologies/ml-agents: The Unity Machine Learning Agents Toolkit (ML-Agents) is an open-source project that enables games and simulations to serve as environments for training intelligent agents using deep reinforcement learning and imitation learning.](https://github.com/Unity-Technologies/ml-agents)

[GitHub - gonglei007/GameDevMind: 最全面的游戏开发技术图谱。帮助游戏开发者们在已知问题上节省时间，省出更多的精力投入到更有创造性的工作中去。](https://github.com/gonglei007/GameDevMind)
Unity 游戏引擎的程序生成库[GitHub - Syomus/ProceduralToolkit: Procedural generation library for Unity](https://github.com/Syomus/ProceduralToolkit)

特效工具集 [GitHub - Unity-Technologies/VFXToolbox: Additional tools for Visual Effect Artists](https://github.com/Unity-Technologies/VFXToolbox)

### Effects

[GitHub - keijiro/TestbedHDRP: Testbed project for Unity HDRP (High Definition Render Pipeline)](https://github.com/keijiro/TestbedHDRP)

[GitHub - QianMo/X-PostProcessing-Library: Unity Post Processing Stack Library | Unity引擎的高品质后处理库](https://github.com/QianMo/X-PostProcessing-Library)

[GitHub - mob-sakai/ParticleEffectForUGUI: Render particle effect in UnityUI(uGUI). Maskable, sortable, and no extra Camera/RenderTexture/Canvas.](https://github.com/mob-sakai/ParticleEffectForUGUI)

### Shader

[GitHub - lettier/3d-game-shaders-for-beginners: 🎮 A step-by-step guide to implementing SSAO, depth of field, lighting, normal mapping, and more for your 3D game.](https://github.com/lettier/3d-game-shaders-for-beginners)

[GitHub - QianMo/Awesome-Unity-Shader: :boat: 关于炫酷的Unity3D Shader | About Cool Unity3D Shaders](https://github.com/QianMo/Awesome-Unity-Shader)

[GitHub - adrian-miasik/unity-shaders: A bunch of shader examples created in Unity (ShaderGraph & Built-in) 🧙✨](https://github.com/adrian-miasik/unity-shaders)

[GitHub - nvjob/nvjob-water-shader-simple-and-fast: NVJOB Simple Water Shaders. Free Unity Asset.](https://github.com/nvjob/nvjob-water-shader-simple-and-fast)

### Collects

https://github.com/baba-s/awesome-unity-open-source-on-github  
https://github.com/RyanNielson/awesome-unity  
https://github.com/michidk/Unity-Script-Collection  
https://github.com/XINCGer/Unity3DTraining  
https://github.com/ThusSpokeNomad/GameNetworkingResources

### Toon Shader

https://github.com/Delt06/urp-toon-shader  
https://github.com/Delt06/toon-rp  
https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample  
https://github.com/JasonMa0012/JTRP

## 资源下载

[Free VFX image sequences and flipbooks | Unity Blog](https://blog.unity.com/engine-platform/free-vfx-image-sequences-flipbooks)

## 学习路径

1. Code Monkey - (Game Script, Multi Player)  
	1. Learn Unity Beginner Intermediate 2023
	2. Learn Unity Multiplayer
2. Third Person Game  
	1. THIRD PERSON MOVEMENT in 11 MINUTES - Unity Tutorial [UCwwn2q4Vys]
	2. THIRD PERSON MOVEMENT in Unity [4HpC--2iowE]
3. Virtual Camera (MainCamera)  
4. Visual Effect Graph
5. Basic Real-Time FX ｜ Simon Verstraete ｜ Games Workshop [kMI-Wro3p9g]
6. Complex Roads in Houdini
	1. Complex Roads in Houdini - Part 1： Solving Intersections [bTlY9ahThdQ]
	2. Complex Roads in Houdini - Part 2： Constructing Geometry [lV8r3pDZZ50]
	3. Complex Roads in Houdini - Part 3： Setting up a Road Tool [EoRHJPN-JI0]
7. Creating Fire, Smoke & Mist Effects with VFX Graph in Unity! (Tutorial) [OCzGXcdyqnQ]
8. FIREWORKS in Unity using VFX Graph! [iCEHarLRCzI]
9. Houdini Engine for Unity ｜ Instancing & Variation [Hw-XcMe7B3E]
10. Intro to Playmaker (2021) [Vx4TxvtqICE]
11. Procedural Generated Pipe
	1. Procedural Generated Pipe - Part 1： Generating Geometry [0Kk0tHp0Ax8]
	2. Procedural Generated Pipe - Part 2： HDA and Unreal Materials [8V8BzEK0cDI]
	3. Procedural Generated Pipe - Part 3： Valves, Connectors and Corners [qgPnDvYvdQk]
	4. Procedural Generated Pipe - Part 4： Cleaning up the Interface [xQ8J2Lj6nXE]
12. The Matrix Awakens： Creating a World ｜ Tech Talk ｜ State of Unreal 2022 [xLVJP-o0g28]
13. The Matrix Awakens： Generating a World ｜ Tech Talk ｜ State of Unreal 2022 [usJrcwN6T4I]
14. Thinking Procedurally ｜ Moritz Schwind ｜ Games Workshop [moRNVJwSKYA]


# Unreal

## 技术

作者个人对虚幻引擎中的GameplayAbilitySystem（GAS）的理解。[GitHub - tranek/GASDocumentation: My understanding of Unreal Engine 5's GameplayAbilitySystem plugin with a simple multiplayer sample project.](https://github.com/tranek/GASDocumentation)