### 分别使用sgd、RMSprop、Adagrad、Adadelta、Adam作为优化器完成2.7节中客户流失预测模型

### 比较了相同模型使用各种优化器时的收敛精度和代价函数的损失率，从而看出不同优化器的特性

### 将迭代过程记录到history文件中，绘制折线图并显示和存储

### keras中loss与val_loss的关系：loss是训练集的损失值，val_loss是测试集的损失值
--------------------------------------------------------------------------------
- 2.8 使用不同优化器进行比较-迭代过程数据存储部分.py

- 2.8 使用不同优化器进行比较-迭代过程显示部分.py

  history = model.fit(x_train, y_train）与history=pickle.load(file_pi)的history格式上略有不同，可百度差异
 
--------------------------------------------------------------------------------
### 以下是loss与val_loss的变化反映出训练走向的规律总结：

- train loss 不断下降，test loss不断下降，说明网络仍在学习;（最好的）

- train loss 不断下降，test loss趋于不变，说明网络过拟合;（max pool或者正则化）

- train loss 趋于不变，test loss不断下降，说明数据集100%有问题;（检查dataset）

- train loss 趋于不变，test loss趋于不变，说明学习遇到瓶颈，需要减小学习率或批量数目;（减少学习率）

- train loss 不断上升，test loss不断上升，说明网络结构设计不当，训练超参数设置不当，数据集经过清洗等问题。（最不好的情况）

## Tensorflow中不同优化器说明

  标准梯度下降法：先计算所有样本汇总误差，然后根据总误差来更新权值。tensorflow这里提供的tf.train.GradientDescentOptimizer相当于是SGD。
  
  tf.train.GradientDescentOptimizer
  
  自适应矩估计
  
  tf.train.AdamOptimizer
  
  动量优化器
  
  tf.train.MomentumOptimizer
  
  均方根优化器
  
  tf.train.RMSPropOptimizer
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
