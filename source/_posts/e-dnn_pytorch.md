---
title: "[Exercise] Deep Neural Network in Pytorch"
date: 2019-06-30 14:15:35
categories:
- exercise
tags:
- deep learning
---

# Deep Neural Network in Pytorch

[![](https://img.shields.io/badge/Github-Source%20Code-blue)](https://github.com/dbddqy/Note/tree/master/Deep_Learning/exercise_dnn_pytorch)

A network with 3 hidden layers, each contains 5 neurons.

```python
class Net(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc1 = nn.Linear(2, 5)
        self.fc2 = nn.Linear(5, 5)
        self.fc3 = nn.Linear(5, 5)
        self.fc4 = nn.Linear(5, 5)
        self.fc_out = nn.Linear(5, 2)

    def forward(self, x):
        x = F.relu(self.fc1(x))
        x = F.relu(self.fc2(x))
        x = F.relu(self.fc3(x))
        x = F.relu(self.fc4(x))
        x = self.fc_out(x)
        return F.softmax(x, dim=-1)
```

Result:

![](https://github.com/dbddqy/Note/raw/master/Deep_Learning/exercise_dnn_pytorch/result.png)

Result of using too many neurons (overfitting):

![](https://github.com/dbddqy/Note/raw/master/Deep_Learning/exercise_dnn_pytorch/overfitting.png)