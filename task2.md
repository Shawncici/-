## Keras使用
1.convolution2D 是2维卷积
2.MaxPooling2D 是2维最大池化
3.Flatten 数据扁平化（降维）为1维数据，从而输入
4.padding 方式有 same和valid
5.kernel_size 卷积窗口大小
6.filters 卷积核/滤波器个数
7.strides 步长

## random_state的应用
1.划分训练集和测试集的类 train_test_split
xtrain,xtest,ytrain,ytest = train_test_split(X,y,test_size=0.2,random_state=42)
随机数种子控制每次划分训练集和测试集的模式，取值不变时得到的结果一模一样，取值改变时，划分结果不同。
若不设置该参数，则函数会选择一种随机模式，得到的结果也不同。
