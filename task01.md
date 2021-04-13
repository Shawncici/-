# 语音识别的不同模型
## 基于CNN的分类模型
CNN分类模式是参考图片分类形式，根据声音的频谱进行分类。
CNN模型——convolutional Neural Networks 卷积神经网络，属于深度神经网络DNN的一种。
![image](https://user-images.githubusercontent.com/33819026/114294210-9560f800-9acf-11eb-9965-f2b02f9cc8b2.png)

弊端是：不能够准确识别人说话的文本，但用于区分不同类别的声音是足够的
## 基于LSTM的分类模型
通过对声音数据进行预处理、提取声音数据的特征、根据特征划分数据集，并对模型进行训练，达到对声音数据分类的任务。
LSTM模型是一种特殊的RNN模型，能够学习长期规律

## 环境配置
需要用到：
1.TensorFlow 2.0
2.keras
3.sklearn
4.librosa。 librosa库是用于音频、音乐分析、处理的库
### TensorFlow
TensorFlow是由谷歌开发的一个开源、基于python的机器学习框架，能够应用在图形分类、音频处理、推荐系统和自然语言处理等应用场景下。
### Keras
keras是用纯python编写，基于TensorFlow的深度学习框架。
keras是一个高层神经网络API，支持快速实验，能够快速把idea转换为结果，尤其适用于以下需求：
1）简易和快速的原型设计
2）支持CNN和RNN，或者二者结合
3）无缝CPU和GPU切换。
keras的模块结构
![image](https://user-images.githubusercontent.com/33819026/114298040-e29c9400-9ae6-11eb-8720-05e2257929d1.png)
使用keras搭建神经网络的流程
![image](https://user-images.githubusercontent.com/33819026/114298056-f811be00-9ae6-11eb-8996-ee271e1a5141.png)
#### Keras模型
keras有两种模型：Sequential models和Function API两种
1）Sequential models 序贯式，是函数式的一种特殊情况。其特征为：单输入、单输出，一条路通到底，层与层之间是相邻关系，没有跨层链接。这种模型编译速度快，操作简单；
2）Function API 函数式模型：多输入、多输出，层与层之间任意链接，编译速度较慢
## sklearn
sklearn是机器学习中常用的第三方模块，对常用的机器学习方法进行了封装，包括回归（Regression）、降维（Dimensionality Reduction）、分类（classification）、聚类（Clustering）等方法。
引入数据库的方式主要有以下：
from sklearn import datasets #引入数据集，sklearn包含众多数据集
from sklearn.model_selection import train_test_split #将数据分为测试集和训练集
from sklearn.neighbors import KNeighborsClassifier #利用临近点方式训练数据
## librosa
librosa是一个用于音频、音乐分析、处理的python工具包，一些常见的时频处理、特征提取、绘制声音图形等功能均有。
读取音频
import librosa
y,sr=librosa.load('./beat.wav')  #sr为采样率
提取特征
mlspec=librosa.feature.melspectrogram(y,sr,n_fft=1024,hop_length=512,n_mels=128)
## 文件夹地址拼接
在MAC电脑中，路径用 /
Windows电脑中，路径用 \
在python中，文件夹路径的结尾带有斜杠，
os.path.join（）函数就是用来补足路径之间的斜杠；
