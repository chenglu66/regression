# regression
用线性回归找到最佳拟合曲线
回归一般就是拟合，即用数据的来拟合结果，所以就有一个问题怎么判别拟合好坏，怎么去拟合，
线性回归就是变量之间的线性组合。那么误差的好坏用最小二乘来衡量。感觉没什么了，
当问题欠拟合时即选取的模型不足以刻画整体数据。因为模型可能比较复杂，但是强行提高模型复杂度可能会过拟合
常用的办法是局部加权线性回归。选择与这个点相近的点而不是所有的点做线性回归。
就好像SVM分类器一样，就是我用需要点而不是所有点来预测数据，因为一些点可能和改点无关，比如马尔可夫链。所以用最相关的点来预测是最好的。
而相关怎么定义，定然是距离信息。说白了就是距离近的加权和的系数大点
基于这个思想，便产生了局部加权线性回归算法。在这个算法中，其他离一个点越近，权重越大，对回归系数的贡献就越多。
下面就是怎么刻画这个信息。这个我是想不出来，不过每个点都要给权重，距离远就小，距离近就大，负指数函数满足，但我还要保证可调，所以用高斯核
通过高斯核函数可以知道，k值越大，用于训练的点也会多些。越小用于训练的点也会少些。
可以想象这种方法得到的回归模型效果非常好，但是计算起来非常复杂，特别是数据比较多的时候。
当然这样想加入引入线性回归很容易过拟合，因为要求的指标是最小二乘，解决办法正则化，最小二乘相当于最大似然概率。
怎么衡量预测的好坏，标称可以用错误率来区分，回归问题可以用相关系数。






下面没啥说的就是运算了，看一个具体的例子：
预估玩具的价格：那么玩具价格和哪些因素有关，怎么衡量。

