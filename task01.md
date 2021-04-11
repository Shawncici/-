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
3.keras
4.sklearn
5.librosa。 librosa库是用于音频、音乐分析、处理的库
### TensorFlow
TensorFlow是由谷歌开发的一个开源、基于python的机器学习框架，能够应用在图形分类、音频处理、推荐系统和自然语言处理等应用场景下。
### Keras
keras是用纯python编写，基于TensorFlow的深度学习框架。
keras是一个高层神经网络API，支持快速实验，能够快速把idea转换为结果，尤其适用于以下需求：

