## Speaker classification

## 目標

學會怎麼用transformer

## Task

predict說話的人是哪一個speaker

## Transformer- Pytorch packages

* [TRANSFORMERENCODERLAYER](https://pytorch.org/docs/stable/generated/torch.nn.TransformerEncoderLayer.html)

```!
CLASS
torch.nn.TransformerEncoderLayer(d_model, nhead, dim_feedforward=2048, dropout=0.1, activation=<function relu>, layer_norm_eps=1e-05, batch_first=False, norm_first=False, bias=True, device=None, dtype=None)
```

* [TRANSFORMERENCODER](https://pytorch.org/docs/stable/generated/torch.nn.TransformerEncoder.html)

```!
CLASS
torch.nn.TransformerEncoder(encoder_layer, num_layers, norm=None, enable_nested_tensor=True, mask_check=True)
```

* [SEQUENTIAL](https://pytorch.org/docs/stable/generated/torch.nn.Sequential.html)

```python
# example
# Using Sequential to create a small model. When `model` is run,
# input will first be passed to `Conv2d(1,20,5)`. The output of
# `Conv2d(1,20,5)` will be used as the input to the first
# `ReLU`; the output of the first `ReLU` will become the input
# for `Conv2d(20,64,5)`. Finally, the output of
# `Conv2d(20,64,5)` will be used as input to the second `ReLU`
model = nn.Sequential(
          nn.Conv2d(1,20,5),
          nn.ReLU(),
          nn.Conv2d(20,64,5),
          nn.ReLU()
        )
```

* [LINEAR](https://pytorch.org/docs/stable/generated/torch.nn.Linear.html)

```!
CLASS
torch.nn.Linear(in_features, out_features, bias=True, device=None, dtype=None)
```

## Resources

[作業說明](https://speech.ee.ntu.edu.tw/~hylee/ml/ml2021-course-data/hw/HW04/HW04.pdf)
[code說明](https://youtu.be/EPerg2UnGaI?si=fah3vnbuxYov7lqd)
[Dataset from Kaggle](https://www.kaggle.com/competitions/ml2021spring-hw4)
[Download dataset form cloud steps](https://drive.google.com/drive/folders/13T0Pa_WGgQxNkqZk781qhc5T9-zfh19e)

### [程式碼](https://colab.research.google.com/drive/138SAn1b2-nkJX_sU5RmGyHFYNrDCjauP?usp=sharing)
