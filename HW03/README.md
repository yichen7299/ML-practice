## HW3 CNN
### 目標:
1. 用CNN做image classification
2. 用data augmentations提升performance
3. 了解怎麼使用unlabeled data

### Task: 把食物照片做分類(有11個類別)

#### Data augmentation
Data augmentation 是 deep learning 中常見從資料方面緩解 overfitting 的手段，尤其適合資料量不足或各類別資料量不平均造成的問題。
一張圖片經過旋轉、調整大小、比例尺寸，或者改變亮度色溫、翻轉等處理後，我們人眼仍能辨識出來是相同的相片，但是對機器來說那可是完全不同的新圖像了，因此， Data augmentation就是將dataset中既有的圖片予以修改變形，以創造出更多的圖片來讓機器學習，彌補資料量不足的困擾。
[Data Augmentation 資料增強](https://chtseng.wordpress.com/2017/11/11/data-augmentation-%E8%B3%87%E6%96%99%E5%A2%9E%E5%BC%B7/)

#### Error
<font color="#f00">RuntimeError</font>: DataLoader worker (pid 15450) is killed by signal: Aborted. 
問題:
* 透過設定num_wokers, DataLoader實例可以使用多少子進程進行數據加載，進而加快訓練速度
* 默認情況下設定為0，代表在主進程內加載數據
* 但num_wokers不能無限制設定到很大，機器硬體跑不起來，下面是google colab跳的提示:
:::warning
UserWarning: This DataLoader will create 8 worker processes in total. Our suggested max number of worker in current system is 2, which is smaller than what this DataLoader is going to create. Please be aware that excessive worker creation might get DataLoader running slow or even freeze, lower the worker number to avoid potential slowness/freeze if necessary.
:::


### Resources
[作業說明](https://speech.ee.ntu.edu.tw/~hylee/ml/ml2021-course-data/hw/HW03/HW03.pdf)
[Dataset from Kaggle](https://www.kaggle.com/competitions/ml2021spring-hw3/data)

### [程式碼](https://colab.research.google.com/drive/1MWicBbkf-y4YQ2MfRVImVIc5XxEHXl_W?usp=sharing)