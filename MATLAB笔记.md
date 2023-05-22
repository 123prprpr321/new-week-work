# **四种二维图表**

### plot线图

**grid on 显示网格**

**plot（）绘制简单线图，如果只传入一个矩阵，那么索引作为x，元素作为y，绘制折线图**

x = 0:0.05:30;  表示0-30，每隔0.05取一个值  也就是[0 , 0.05 ,0.1 ...... 29.05 , 30]

plot（x，y）函数传入两个参数时，x表示x轴，y用一个矩阵或者函数，参数为传入的x值



**xlabel（“横坐标轴”）**

**ylabel（“纵坐标轴”）**

**xlabel 和 ylabel可以取得标题**

**修改线宽**

plot函数传入'LineWidth' 然后逗号接上数字

![image-20230521101726752](C:\Users\Pluto\AppData\Roaming\Typora\typora-user-images\image-20230521101726752.png)



axis（）设置轴范围

axis（[0 20 -2  2]）  注意不要逗号  依次是x轴起始 x轴末尾  y轴起始 y轴末尾



**多组函数显示在同一张图上**

plot（）向其中多次传入

y1 = sin（x） y2 = cos（x）

plot（x，y1，x，y2）

### bar条形图

bar函数创建垂直条形图

barh函数创建水平条形图



exp表示自然底数e

### polarplot极坐标图

![image-20230521102615033](C:\Users\Pluto\AppData\Roaming\Typora\typora-user-images\image-20230521102615033.png)

.*  对应相乘，绘图常用

polarplot（x，y）x表示角度，y表示长度

### scatter散点图

绘制x和y值的散点图

**就是使用scatter（x，y）这个函数不连线**



**randn函数** 

![image-20230521103205051](C:\Users\Pluto\AppData\Roaming\Typora\typora-user-images\image-20230521103205051.png)

生成x行y列的数组



# 三维图

**使用surf函数做三维曲面图**

surf传入三个参数X，Y，Z

这三个参数中，Z需要与X，Y有关，所以需要先创建Z函数，要不然全是离散的

**创建（x，y）**

**meshgrid函数**

[x,y] = meshgrid(-2:0.2:2);

这里x和y都是-2到2 step为0.2  相当于xoy平面上这些点



![image-20230521105451473](C:\Users\Pluto\AppData\Roaming\Typora\typora-user-images\image-20230521105451473.png)

步骤就是先用meshgrid构造xy范围，然后构造z函数

三个参数传入surf绘制三维图



colormap hsv  更改颜色 还有winter和summer等色调



colorbar可以显示对应颜色对应的数值

## 子图

subplot（a，b，c）

其中a b 表示a行b列 ，一共可以放a*b个图  c表示放在第几个位置

```matlab
subplot(1,2,1); surf(x.^2); title('ahh');
```

## 导入数据

直接导入Excel文件、



# 模型

线性规划 ：尽量多 最多  理论最大  最合理

多目标规划[(9条消息) 数学建模——lingo实现多目标规划_lingo求解多目标线性规划_狗头狗不狗的博客-CSDN博客](https://blog.csdn.net/qq_43649786/article/details/98359558)

[(9条消息) 数学建模（3.9）多目标规划_狗头狗不狗的博客-CSDN博客](https://blog.csdn.net/qq_43649786/article/details/98358368)



灰色预测

最短路径（DJ算法）

最小生成树 