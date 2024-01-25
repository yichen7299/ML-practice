## HW2 Classification
分成兩個小題
## 1. Phoneme Classification
目標: 對input音節做分類(multiclass classification)，看是屬於哪一類型的音節
[作業說明](https://speech.ee.ntu.edu.tw/~hylee/ml/ml2021-course-data/hw/HW02/HW02.pdf)
[Dataset from Kaggle](https://www.kaggle.com/c/ml2021spring-hw2/data)

### [程式碼](https://colab.research.google.com/drive/1ZFEgwNGcLNoGf7iQjlMhPnNFw1qMGvC8?usp=sharing)

## 2. Hessian Matrix
目標: 判斷目前訓練的模型是屬於 local minima-like point, saddle point, or none of the above
透過Hessian Matrix來判斷

### Gradient Norm / Minimal Ratio
In this homework, we assume that 
● gradient norm < 1e-3 and minimum ratio > 0.5 => local minima like, 
● gradient norm < 1e-3 and minimum ratio <= 0.5 => saddle point, 
● gradient norm >= 1e-3 => none of the above.

程式碼:RuntimeError:
The default behavior has changed from using the upper triangular portion of the matrix by default to using the lower triangular portion.
(Skip)

### [程式碼](https://colab.research.google.com/drive/1hIGgC970GnT9RC0om6ZeSIrjTRq4AhkH?usp=sharing)