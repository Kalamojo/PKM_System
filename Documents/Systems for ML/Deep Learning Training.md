What are the steps in a DNN supervised training loop?

---

1. Read a single batch
2. Forward pass: perform matrix multiplies to compute output activations
3. Compute loss on this batch
4. Backward pass: matrix multiplies to compute gradients of the loss w.r.t. parameters via backpropagation
5. Optimizer step: use gradients to update the weights or parameters such that loss is gradually reduced