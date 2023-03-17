#DataLoader 
#PytorchBasics
[[PytorchBasics]]
PyTorch provides two data primitives: 
	`torch.utils.data.DataLoader` 
and 
	`torch.utils.data.Dataset` 
that allow you to use pre-loaded datasets as well as your own data. 
`Dataset` stores the ==samples and their corresponding labels==
`DataLoader` wraps an **iterable** around the `Dataset` to **enable easy access** to the samples