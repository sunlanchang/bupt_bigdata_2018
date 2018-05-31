<div align="center">
  <img src="https://www.tensorflow.org/images/tf_logo_transp.png"><br><br>
</div>

-----------------


| **`Documentation`** |
|-----------------|
| [![Documentation](https://img.shields.io/badge/api-reference-blue.svg)](https://www.bipt.edu.cn/) |


# 北京邮电大学-数据挖掘竞赛-2018（tensorflow版本）
## description

利用GPU加速TensorFlow计算，快速迭代模型。

## 框架流程图

![流程图](picture/流程图.svg)

## 环境

| 环境      | 版本 | Python模块    | 版本 |
| ---    | ---    | ---      | --- |
| Ubuntu | 16.04  | tensorflow | 1.8 |
| Anaconda | 5.1 | numpy|
| Python | 3.6 | pandas|
| Jupyter lab | 0.31.5 | matplotlib|

## 数据预处理

- 合并1到10月所有csv文件
- 构造训练数据集
- 对每一个地点的用户ID总数统计，构造标签列。

> 合并文件利用pandas读取每个文件，将每个文件赋值给一个DataFrame，最后利用`pd.concat()`合并成为一个DaraFrame写入文件。

合并的文件如下图所示,共252014行：

|地点|时间|人数|
|-|-|-|
|12|2017-11-28 12|11878|
|12|2017-11-20 12|11171|
|12|2017-11-23 12|10740|
|12|2017-11-21 12|10069|
|...|...|...|

## 提取特征

- 提取已有的基本的特征
- 手工构造特征
- 提取特征列利用pandas对时间特征的解析，分离出日、月、小时等特征列，

| 特征列 |building|cat|day|hour|is_weekend|	loc_id|	month|weekday|
| - | - | - | - | - | - | - | - | - |
|特征列含义|建筑物编号|建筑物类别|日|小时|是否周末|地点ID|月|星期|

## 选择模型

采用`sklearn`和`tensorflow`模型多次训练模型，选择一个模型后优化模型。

- 其中`tensorflow`采用`High Level APIs`中的`Estimator`，快速开发迭代模型取得了较为不错的结果，并且可以灵活的改变神经网络的架构，不需要修改大量的代码。

### Linear Regrassor

- 根据月份将数据可视化后（如下图所示），发现使用线性模型并不适合数据的拟合。

![月份人数](picture/月份人数.png)

### SVM

使用`sklearn.model_selection.train_test_split()`划分数据集为训练数据集和验证数据集，使用`sklearn.svm.SVC()`训练模型。

### DNN Regrasor

采用TensorFlow中

## 参数选择



## 超参选择

采用`tensorflow.estimator.DNNRegrasor()`默认参数。
```
__init__(
    hidden_units,
    feature_columns,
    model_dir=None,
    label_dimension=1,
    weight_column=None,
    optimizer='Adagrad',
    activation_fn=tf.nn.relu,
    dropout=None,
    input_layer_partitioner=None,
    config=None,
    warm_start_from=None,
    loss_reduction=losses.Reduction.SUM
)

```

## 模型训练
## 模型评测
## 模型预测
## 其他常用linux命令

`tmux new-session -t $name`  
按照名字创建session


## For more information