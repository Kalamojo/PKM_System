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
> ```cpp
> rayTrace() {  
> 	construct scene representation  
> 	for each pixel  
> 		^ray = computePrimaryViewRay( pixel )  
> 		*hit = first intersection of ^ray with scene (mesh triangles)
> 		color = shade( *hit ) / using "shadow ray"
> 		set pixel color  
> }
> ```

## References
1. [[Rendering]]
2. [[Triangle Mesh]]
3. [[Primary Rays]]
4. [[Secondary Rays]]