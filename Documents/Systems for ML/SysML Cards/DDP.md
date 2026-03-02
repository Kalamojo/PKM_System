---
noteId: 1772491633892
---

How does Distributed Data Parallelism (DDP) optimize the synchronization of gradients compared to a naive approach?

---

- Naive solution: wait for the entire backward pass to complete before issuing an [[All-Reduce]]
- Improvement: issues all-reduces as gradient tensors become ready
- Furthermore: combines multiple all-reduces into a single operation using "buckets"