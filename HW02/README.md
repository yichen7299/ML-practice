## HW2 Classification

分成兩個小題

## 1. Phoneme Classification

### task

對input音節做分類(**multiclass classification**)，看是屬於哪一類型的音節

1. baseline 0.5
2. concat n frames, add layers 0.65
3. adjust batchnorm, dropout 0.75
4. HARD- using RNN to sequence labeling 0.83

### Mein model

#### DNN

TODO: apply batch normalization and dropout for strong baseline.
Reference:
<https://pytorch.org/docs/stable/generated/torch.nn.BatchNorm1d.html> (batch normalization)
<https://pytorch.org/docs/stable/generated/torch.nn.Dropout.html> (dropout)

```python
class BasicBlock(nn.Module):
    def __init__(self, input_dim, output_dim):
        super(BasicBlock, self).__init__()

        self.block = nn.Sequential(
            nn.Linear(input_dim, 64),
            nn.ReLU(),
            nn.Linear(64, output_dim),
            nn.ReLU(),
            nn.BatchNorm1d(output_dim),
            nn.Dropout(p=0.5)
        )

    def forward(self, x):
        x = self.block(x)
        return x
```

acc ≈ 0.47935

#### DNN 根據baseline的改善

* [data preprocessing部分]
  * 做每個類別數量統計
* [parameters]
  * batch size = 2048 (original: 64)
  * 修改epoch 和 learning rate
* [Model]
  * 三層NN改成六層
  * 加入batch normalization
  * activation function: sigmoid改成RELU
  * 加入dropout rate

acc ≈ 0.755

### Sources

[2023作業說明](https://speech.ee.ntu.edu.tw/~hylee/ml/ml2023-course-data/HW02+%E8%81%BD%E6%B8%AC.pdf)
[2021作業說明](https://speech.ee.ntu.edu.tw/~hylee/ml/ml2021-course-data/hw/HW02/HW02.pdf)
[Dataset from Kaggle](https://www.kaggle.com/c/ml2021spring-hw2/data)

### [我的hw2程式碼](https://colab.research.google.com/drive/1084OFWDsoSKlUIHJZe7PxWvNHLLp2EA_?usp=sharing)

### [2023程式碼](https://colab.research.google.com/drive/1itfh89-wVeR5c5_St5W0hvYJyQKITVEX?usp=sharing)
