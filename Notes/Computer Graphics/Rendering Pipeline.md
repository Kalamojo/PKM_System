---
aliases:
  - Computer Graphics Pipeline
subject: Computer Graphics
tags:
  - masters
---
# Rendering Pipeline

>[!note]
> An established framework in [[Computer Graphics]] to transform a 3-Dimension scene into a 2-Dimension representation on a screen.

> [!method]
> ```mermaid
> graph TD
> 
> id1[Input Data] --> id2[Transformation, 3D to 2D]
> id2[Transformation, 3D to 2D] --> Rasterization
> Rasterization --> Shading
> Shading --> Z-buffering
> 
> class Rasterization,Z-buffering internal-link;
> ```

>[!info]
> Essentially, this is a whole bunch of math to turn a 3D model (in the form of [[Triangle Mesh]] arrays) into a pixel-based image.

## References
1. [[Rendering]]
2. [[Computer Graphics]]