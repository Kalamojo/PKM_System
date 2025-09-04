---
alias: []
subject: Computer Graphics
tags:
  - masters
---
# Ray Tracing

>[!note]
> A technique for modeling the way light travels for the purpose of [[Rendering]] digital images.

>[!method] 
> Ray tracing naive approach:
> 
> ```cpp
> rayTrace() {
> 	construct scene representation
> 	for each pixel
> 		^ray = computePrimaryViewRay( pixel )
> 		//*firstHit = first intersection of ^ray with scene (mesh triangles)
> 		for each meshTriangle
> 			hit = point where ^ray meets meshTriangle
> 			if hit is closer than *firstHit (to camera): *firstHit = hit
> 		color = shade( *firstHit ) / using "shadow ray"
> 		set pixel color
> }
> ```
> 
> While this approach works, it is very expensive as there is no spatial awareness involved. As for as the naive approach is concerned, every single triangle in the scene could possibly be hit by the ray, and could also be the front-most object (visible by the camera), so each one must be checked for an [[Intersection]].
> 
> To improve this, [[Ray Tracing Acceleration]] techniques are needed.

> [!example]
> ![[Pasted image 20250904103547.png|center|600]]

## References
1. [[Rendering]]
2. [[Triangle Mesh]]
3. [[Primary Rays]]
4. [[Secondary Rays]]