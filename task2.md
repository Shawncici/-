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

## librosa
1.主要用于提取音频数据
主要函数有.load()——音频读取函数、resample——重采样函数、stft()短时傅里叶变换函数
常用的频谱特征的提取方法主要有Mel Spectrogram、MFCC、CQT
melspectrogram（y,sr,S,n_fft) 其中n_fft指的是窗的大小，
mfcc（y,sr,S,n_mfcc)
2.绘图显示
常用的显示方式有：频谱显示函数包括specshow（）、波形显示函数waveplot（）；
其中specshow（data[x_coords,y_coords,x_axis,..])


waveplot（y,[,sr,max_points,x_axis,..])



## librosa.load()   
读取音频文件，默认采样率为22050，如果希望以原始采样率读取文件，要设置sr=None
