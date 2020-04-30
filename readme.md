## 文件说明
faceTask.ipynb是主要的代码文件，请用jupyter notebook打开。
sample.mp4是样例视频。

## 使用库和模型
本程序使用dlib和opencv库进行视频帧的人脸提取，关键点检测和人脸对齐，使用pytorch进行模型的加载。

性别和年龄检测均使用自己训练的resnet18模型，而表情检测使用了github.com/WuJie1010/Facial-Expression-Recognition.Pytorch中的现有代码。

## 函数说明
getFaceFromVideo()函数能从视频中提取出帧并将帧中的人脸框出且单独输出到文件。输出在faces文件夹中。

视频使用的是自己录的样例视频。

getFeaturePoints()函数能从人脸照片中识别68个关键点并输出到文件。输出在landmarks文件夹。

getAlignment()函数能进行人脸对齐。输出在align文件夹。

getAge()函数从age-recognition/test文件夹中按顺序读取图片文件（目前只读取样例文件，可以用循环读取所有文件）并用模型输出所有图片预测的年龄。

输出为0-100之间的整数。

getGender()函数从gender-recognition/test文件夹中按顺序读取图片文件（目前只读取样例文件，可以用循环读取所有文件）并用模型输出所有图片预测的性别。

输出为male（结果为0）或female（结果为1）。

表情预测需要在Facial-Expression-Recognition.Pytorch-master文件夹下使用python visualize.py命令，图片需要放在Facial-Expression-Recognition.Pytorch-master/images文件夹下。

输出为anger, disgust, fear, happy, sad, surprised, normal（生气，厌恶，恐惧，开心，伤心，惊讶，中性）七个中的一个。

## 