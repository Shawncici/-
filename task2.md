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

## 声谱图
![image](https://user-images.githubusercontent.com/33819026/114873569-fc631180-9e2d-11eb-8707-7b9183a16a4a.png)
这段语音被分为很多帧，每帧语音都对应于一个频谱（通过短时FFT计算），频谱表示频率与能量的关系。在实际使用中，频谱图有三种，即线性振幅谱、对数振幅谱、自功率谱（对数振幅谱中各谱线的振幅都作了对数计算，所以其纵坐标的单位是dB（分贝）。这个变换的目的是使那些振幅较低的成分相对高振幅成分得以拉高，以便观察掩盖在低幅噪声中的周期信号）。
![image](https://user-images.githubusercontent.com/33819026/114873774-392f0880-9e2e-11eb-9b04-d40e52ac76d1.png)
我们先将其中一帧语音的频谱通过坐标表示出来，如上图左。现在我们将左边的频谱旋转90度。得到中间的图。然后把这些幅度映射到一个灰度级表示（也可以理解为将连续的幅度量化为256个量化值？），0表示黑，255表示白色。幅度值越大，相应的区域越黑。这样就得到了最右边的图。那为什么要这样呢？为的是增加时间这个维度，这样就可以显示一段语音而不是一帧语音的频谱，而且可以直观的看到静态和动态的信息。
这样我们会得到一个随着时间变化的频谱图，这个就是描述语音信号的spectrogram声谱图。
![image](https://user-images.githubusercontent.com/33819026/114873883-582d9a80-9e2e-11eb-91cb-4bf0b9ad019f.png)




