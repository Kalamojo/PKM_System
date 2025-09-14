---
aliases: []
subject: Computer Graphics
tags:
  - masters
---
# Implicit Surfaces

>[!note]
> A surface that is implied by a [[Function]] $f(\boldsymbol{p})=0$, creating a [[Sets|Set]] of zeros for points $\boldsymbol{p}$.

> [!math]
> $$f(\boldsymbol{p})=0$$
> where
> $$f: R^3 \rightarrow R, \boldsymbol{p} = (x,y,z)$$

> [!method]
> To find the [[Ray-Surface Intersection]]:
> Given a ray with origin $\boldsymbol{o}$, direction $\boldsymbol{d}$,
> $$\boldsymbol{p}(t)=\boldsymbol{o} + t\boldsymbol{d},$$
> $$\boldsymbol{p},\boldsymbol{e},\boldsymbol{d} \in R^3, t \in R,$$
> solve for $t$ such that
> $$f(\boldsymbol{p}(t))=0$$

> [!example]
> ![[Pasted image 20250913222327.png|center|600]]

> [!example] Types
> - [[Signed Distance Function]]

## References
1. 