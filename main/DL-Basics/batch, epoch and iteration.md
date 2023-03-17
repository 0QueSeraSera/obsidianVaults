# definition
## epoch
==One _Epoch_ is when an ENTIRE dataset is passed forward and backward through the neural network only ONCE==
Since one _epoch_ is too big to feed to the computer at once we divide it in several smaller _batches_
##### Why we use more than one Epoch?
passing the entire dataset through a neural network is not enough.
- limited dataset 
- **Gradient Descent** which is an **_iterative_** process.

## batch
==divide dataset into Number of Batches or sets or parts.==
batch size:
Total **number of training examples** present in a single batch.

## Iteration
==Iterations is the number of batches needed to complete one epoch==
`The number of batches is equal to number of iterations for one epoch`
We can divide the dataset of 2000 examples into batches of 500 then it will take 4 iterations to complete 1 epoch

take pytorch for example:
This is the training skeleton for **one epoch**

```
def train(dataloader, model, loss_fn, optimizer):
    size = len(dataloader.dataset)
    model.train()
    for batch, (X, y) in enumerate(dataloader):
        X, y = X.to(device), y.to(device)

        # Compute prediction error
        pred = model(X)
        loss = loss_fn(pred, y)

        # Backpropagation
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()

        if batch % 100 == 0:
            loss, current = loss.item(), batch * len(X)
            print(f"loss: {loss:>7f}  [{current:>5d}/{size:>5d}]")
```
