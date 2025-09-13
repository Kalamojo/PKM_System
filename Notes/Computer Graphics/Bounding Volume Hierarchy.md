---
aliases:
  - BVH
subject: Computer Graphics
tags:
  - masters
---
# Bounding Volume Hierarchy

>[!note]
> A geometric [[Tree]] structure that groups all objects into bounding volumes (boxes), with each box potentially containing sub-group volumes.

> [!method]
> In the context of [[Ray Tracing]], this structuring of objects allows for a much-reduced [[Time Complexity]] for measuring each trace. The exact complexity is $\theta (\log{n})$, since its runtime is proportional to the depth of the subgroups.
> 
> In this approach, rather than checking every object in a scene for [[Intersection|intersections]], bounding boxes are filtered by their intersections with the trajectory of a ray. For each of the remaining, intersected boxes, the standard intersection check for hits is performed for each child, and recursively for sub-groups. 

> [!example]
> ![[Pasted image 20250904114416.png|center|600]]

## References
1. [[Data Structures]]
2. [[Recursion Tree]]