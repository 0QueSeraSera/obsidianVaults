[[PytorchBasics]]
https://pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html
`torch.autograd` is PyTorch’s ==automatic differentiation== engine that powers neural network training

## background

Training a NN happens in two steps:
**Forward Propagation**: In forward prop, the NN makes its best guess about the correct output. It runs the input data through each of its functions to make this guess.

**Backward Propagation**: In backprop, the NN adjusts its parameters proportionate to the error in its guess. It does this by traversing backwards from the output, collecting the derivatives of the error with respect to the parameters of the functions (_gradients_), and optimizing the parameters using gradient descent.



We create two tensors `a` and `b` with `requires_grad=True`. This signals to `autograd` that ==every operation on them should be tracked==.
```
import torch
a = torch.tensor([2., 3.], requires_grad=True)
b = torch.tensor([6., 4.], requires_grad=True)
```
