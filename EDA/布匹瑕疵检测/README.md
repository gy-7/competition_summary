## 数据集来源：

[布匹瑕疵检测数据集-阿里云天池 (aliyun.com)](https://tianchi.aliyun.com/dataset/dataDetail?dataId=79336)



## 分析：

分析数据集中 train 集的每个类别的 bboxes 数量分布情况。因为训练集分了两个：train1，train2。先根据两个数据集的 anno_train.json 文件分析类别分布。

| 数据集 | bbox数量 | 缺陷图片数量 | 正常图片数量 |
| ------ | -------- | ------------ | ------------ |
| train1 | 7728     | 4774         | 2538         |
| train2 | 1795     | 1139         | 1125         |
| 总共   | 9523     | 5823         | 3663         |




各类别bbox数量分布：

![image](https://img2022.cnblogs.com/blog/1524748/202201/1524748-20220120160614506-182111829.png)

bbox宽度和高度分布情况：

![image](https://img2022.cnblogs.com/blog/1524748/202201/1524748-20220120160633125-1954551204.png)



bbox宽高比的分布情况：

![image](https://img2022.cnblogs.com/blog/1524748/202201/1524748-20220120160639265-1133132178.png)



:star: 做完所有的EDA后，可以得到以下分析：

+ bbox的类别分布极不平衡，最高的1996，最低的11。
+ bbox的形状差异很大，粗维，稀密档，百脚等宽高比数值很大，部分大于10，说明bbox呈细条状。需要针对此进行修改，生成特殊比例的anchor。
