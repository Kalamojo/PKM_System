# 3-12 Discussion Questions/Topics

## Flash Attention 2022

1. Are there any dependencies between the different blocks of K, Q, and V being computed upon? Could the operations be easily parallelized?
2. In the algorithm outline, what was the reasoning for specific factors in the calculations for block size? Namely, $B_c = \left[\frac{\text{size of SRAM}}{4 \times \text{head dimension}}\right]$ and $B_r = \min \left(\left[\frac{\text{size of SRAM}}{4 \times \text{head dimension}}\right], \text{head dimension}\right)$ ?