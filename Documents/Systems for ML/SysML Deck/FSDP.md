---
noteId: 1772491637693
---

How does Fully Sharded Data Parallelism (FSDP) differ from standard Data Parallelism to save memory?

---

Saves memory by distributing ([[Sharding]]) model parameters within a layer across all GPUs, and then doing an [[All-Gather]] of the parameters before computation starts