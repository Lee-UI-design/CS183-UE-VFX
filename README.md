# CS183

## Project title  
Visual effects application  

## Team members
Guo Menghao(Team Leader):25126075
Done:Blueprint interaction, character movement, grass collision/trigger logic, project integration

Huai Shibo:25126393
Done:Landscape, grass meshes/materials, scene environment

Li Jiahe:25126954
Done:Rain and fog Niagara VFX.And make the video.

Li Yanghao:25124561
Done:Report writing and documentation

Chen Yuhan:25124439
Done:Demo video recording and editing

He Yue:22140093
Done:Presentation slides and oral delivery


## CS concept explained  
This project applies several core computer science ideas in a real-time 3D game engine:

Component-based design. Grass interaction is implemented as reusable Blueprint components (InteractWithGrass_BP) attached to actors (player, AI, projectiles). Logic is separated from scene objects, similar to composition over inheritance in OOP.

Spatial partitioning. Large foliage fields are split into InteractiveFoliageChunk_BP regions so overlap checks and deformation updates only run on nearby chunks, reducing work from O(all grass) to O(nearby chunks).

Collision detection and polling. Interactors periodically perform sphere overlaps (Check Radius / Check Interval) to find affected grass instances—combining geometric query algorithms with time-sliced polling for performance control.

State machines. Each grass instance tracks lifecycle states (FreshlyDeformed → Deformed → UnDeforming) via the InstanceStatus enum, enabling predictable recovery and avoiding redundant updates.

Resource pooling. Material interaction uses a limited channel pool managed by InteractiveGrassManager_BP (GetFreeMaterialInteractionChannel / FreeUpMaterialInteractionChannel), analogous to allocator/pool patterns in systems programming.


## Version 1 summary
Version 1 focused on building a basic outdoor scene.

Features included:

* Static environment
* Basic terrain and vegetation
* Player movement
* Simple scene layout
* Initial lighting setup

At this stage, the environment lacked dynamic interactions and weather effects.

## Version 2 summary  
Version 2 introduced environmental interaction and visual enhancements.

New features included:

* Interactive grass that responds to player movement
* Dynamic rain particle system
* Fog effects for atmosphere
* Improved lighting and scene presentation
* Blueprint-based environmental interactions

These improvements increased realism and player immersion.

## Evidence used for comparison  
The following evidence was used to compare Version 1 and Version 2:

1. Screenshots of both versions
2. Gameplay recordings demonstrating interactions
3. Visual comparison of environmental effects
4. User observations regarding immersion and realism

Comparison Results:

| Feature | Version 1 | Version 2 |
|----------|----------|----------|
| Interactive Grass | No | Yes |
| Rain Effect | No | Yes |
| Fog Effect | No | Yes |
| Environmental Interaction | Limited | Enhanced |
| Visual Immersion | Basic | Improved |

Version 2 provides a more dynamic and engaging experience than Version 1.


## GitHub Link to Codebase  
Repository: 

