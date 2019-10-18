# 00任务
## 1.LearningRateScheduler函数原理
LearningRateScheduler为回调函数callbacks中对学习率进行更改的函数，其又名学习速率定时器，是可以在每一次的epoch中都可以对学习率进行更改的函数，而如何更改则取决于你定义的函数。

## 2.LearningRateScheduler函数使用
![image](https://user-images.githubusercontent.com/50792908/67015870-cd30ee80-f129-11e9-9381-028cd1908f7f.png)
由上方官方文档介绍知，LearningRateScheduler接受两个形参，一位schedule，一为verbose。verbose在这里不多讲，而schedule则是自己定义的函数，schedule接受一个形参(epoch)，同时，Model也可传入schedule中，返回一个浮点数作为新一轮的学习率
使用实例如图
![image](https://user-images.githubusercontent.com/50792908/67016344-a32bfc00-f12a-11e9-8401-9d1046cd1015.png)

## 3.LearningRateScheduler和ReductLROnPlateau函数的比较
回调器中有两个函数均可对学习率进行操作更改，分别为LearningRateScheduler和ReductLROnPlateau函数，但是两者工作原理不一样。LearningRateScheduler是对每一轮的学习率都进行更改矫正。而ReductLROnPlateau如下图所示，
![image](https://user-images.githubusercontent.com/50792908/67016669-264d5200-f12b-11e9-8203-9100f1a88e28.png)
其是在某几轮训练下来，准确率的提高没有达到期望值时才对学习率进行更改。

## 4.LearningRateScheduler使用中的难点
其实难点仍是在于学习率的调整，太大了忽略掉全局最优解、太小了又可能在局部最优解震荡，因此难点仍是在学习率的调整，较为靠谱的思路是参考每一轮的loss，以loss作为权重调解下一轮的学习率。

## 5.LearningRateScheduler中未解决问题
参考Model的loss的话，就需要把每一轮的loss数值传入进去，但是，emmmm能力有限，不知道怎么传，希望知道的大神指导一下~~~~


==========================================================


#  01任务
## 3个加速器在epoch为40下的结果分析比较

##  1.rmsprop优化器


##  2.adam优化器

## 3.SGD优化器
