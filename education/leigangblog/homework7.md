# 1.PaddleGAN实现精准唇形合成-- 物理学界大佬们再次合唱

## 1.1 宋代著名诗人苏轼「动起来」的秘密
坐拥百万粉丝的**独立艺术家大谷Spitzer老师**利用深度学习技术使**宋代诗人苏轼活过来，穿越千年，为屏幕前的你们亲自朗诵其著名古诗~** [点击量](https://www.bilibili.com/video/BV1mt4y1z7W8)近百万，同时激起百万网友热议，到底是什么技术这么牛气？

![](https://ai-studio-static-online.cdn.bcebos.com/c21d8a1de3084b6ca599bc2cda373d3fef4b1a0ae98646f4b629dae14c9bb1f4)


## 1.2 PaddleGAN的唇形迁移能力--Wav2lip
**铛铛铛！！飞桨[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)这就来给大家揭秘，手把手教大家如何实现唇型的迁移，学习过本项目的你们，从此不仅能让苏轼念诗，还能让蒙娜丽莎播新闻、新闻主播唱Rap... 只有你想不到的，没有[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)做不到的！**

本教程是基于[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)实现的视频唇形同步模型**Wav2lip**, 它实现了人物口型与输入语音同步，俗称「对口型」。 比如这样：
![](https://ai-studio-static-online.cdn.bcebos.com/16d0b24fdc5c451395b3b308cf27b59bd4b024366b41457dbb80d0105f938849)

**不仅仅让静态图像会「说话」，Wav2lip还可以直接将动态的视频，进行唇形转换，输出与目标语音相匹配的视频，自制视频配音不是梦！**

本次教程包含四个部分：

- Wav2lip原理讲解
- 下载PaddleGAN代码
- 唇形动作合成命令使用说明
- 成果展示

**若是大家喜欢这个教程，欢迎到[Github PaddleGAN主页](https://github.com/PaddlePaddle/PaddleGAN)点击star呀！下面就让我们一起动手实现吧！**
<div align='center'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/47cea097a0284dd39fc2804a53aa8ee6dad16ffe104641258046eb05af49cd64' width='1000'/>
</div>

## 1.3 Wav2lip模型原理
Wav2lip实现唇形与语音精准同步突破的关键在于，它采用了**唇形同步判别器，以强制生成器持续产生准确而逼真的唇部运动。**

此外，该研究通过在鉴别器中，使用**多个连续帧而不是单个帧，并使用视觉质量损失（而不仅仅是对比损失）来考虑时间相关性，从而改善了视觉质量。**

该wav2lip模型几乎是**万能**的，适用于任何**人脸**、**任何语音**、**任何语言**，对任意视频都能达到很高的准确率，可以无缝地与原始视频融合，还可以用于**转换动画人脸，并且导入合成语音**也是可行的

## 1.4 下载PaddleGAN代码


```python
# 从github上克隆PaddleGAN代码（如下载速度过慢，可用gitee源）
#!git clone https://github.com/PaddlePaddle/PaddleGAN
%cd /home/aistudio/
# 如果已经存在PaddleGAN仓库，可注释下面两行代码，或者从下面安装所需安装包开始
!git clone https://gitee.com/paddlepaddle/PaddleGAN.git
!git checkout develop
```


```python
# 安装所需安装包
%cd /home/aistudio/PaddleGAN
!pip install -r requirements.txt
!pip install imageio-ffmpeg
%cd applications/
```

## 1.5 唇形动作合成命令使用说明

重点来啦！！本项目支持大家上传自己准备的视频和音频， 合成任意想要的**逼真的配音视频**！！![](https://ai-studio-static-online.cdn.bcebos.com/731e8683ff9d415b872981887563621186ea193f251b452183b20b4e7c2c1e4f)



只需在如下命令中的**face参数**和**audio参数**分别换成自己的视频和音频路径，然后运行如下命令，就可以生成和音频同步的视频。

程序运行完成后，会在当前文件夹下生成文件名为**outfile**参数指定的视频文件，该文件即为和音频同步的视频文件。本项目中提供了demo展示所用到的视频和音频文件。具体的参数使用说明如下：
- face: 原始视频，视频中的人物的唇形将根据音频进行唇形合成--通俗来说，想让谁说话
- audio：驱动唇形合成的音频，视频中的人物将根据此音频进行唇形合成--通俗来说，想让这个人说什么


```python
# 视频保存地址：/home/aistudio/work/pp_put.mp4
# 时间10min左右
!export PYTHONPATH=$PYTHONPATH:/home/aistudio/PaddleGAN && python -u tools/wav2lip.py --face /home/aistudio/work/1.mp4 --audio /home/aistudio/work/1.m4a --outfile /home/aistudio/work/pp_put.mp4
```

## 1.6 效果展示
效果不是特别好，以后会改进本项目

![](https://ai-studio-static-online.cdn.bcebos.com/d5c979ec6238476789ca88451b0328f59d58b2b8a02e4a7596bf1ec772e4bba4)



## 1.7 总结
**首先帮大家总结一波：让图片会说话、视频花式配音的魔法--Wav2lip的使用只用三步**：
1. 安装Paddle环境并下载[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)
2. 选择想要「配音/对口型」的对象以及音频内容
3. 运行代码并保存制作完成的对口型视频分享惊艳众人

贴心的送上项目传送门：[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN) 记得点Star关注噢~~
<div align='left'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/c7e2bcd255574e32b10061e0c4a1003a244bb7bd60ad43d394b23183f7390175' width='300'/>
</div>

##  1.8 除了嘴型同步，PaddleGAN还有哪些魔法？

PaddleGAN是只能做「对口型」的应用么？NONONO！当然不是！！
<div align='center'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/f3b7e65df22a4e0fb771db150886dfd93ff602ebf8374fe0bf20e2083f5b1213' width='100'/>
</div>


接下来就给大家展示下PaddleGAN另外的花式应用，如各类**图形影像生成、处理能力**。

**人脸属性编辑能力**能够在人脸识别和人脸生成基础上，操纵面部图像的单个或多个属性，实现换妆、变老、变年轻、变换性别、发色等，一键换脸成为可能；

**动作迁移**，能够实现肢体动作变换、人脸表情动作迁移等等等等。

强烈鼓励大家玩起来，激发PaddleGAN的潜能！

<div align='center'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/461d1f34cf5242fca07d4e333e41f51c099a96017e324531b575a775d0679fc6' width='700'/>
</div>
<div align='center'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/7d2cc83c689c474e8f3c0fa85e58e12b9885b47333d94d4dba4c66e622acf47e' width='700'/>
</div>

欢迎加入官方QQ群（1058398620）与各路技术高手交流~~

<div align='center'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/eb4d10d066c547f19cb373eb72458b12703e1c5b2ea34457b225d958925c2c83' width='250' height='300'/>
</div>

# 2.参考资料

【PaddleGAN的Github地址】:https://github.com/PaddlePaddle/PaddleGAN

【PaddleGAN的Gitee地址】:https://gitee.com/PaddlePaddle/PaddleGAN

【生成对抗网络七日打卡营】课程链接：https://aistudio.baidu.com/aistudio/course/introduce/16651

【生成对抗网络七日打卡营】项目合集:https://aistudio.baidu.com/aistudio/projectdetail/1807841

【图像分割7日打卡营常见问题汇总】
https://aistudio.baidu.com/aistudio/projectdetail/1100155

【PaddlePaddle使用教程】
https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/guides/index_cn.html

【本地安装PaddlePaddle的常见错误】
https://aistudio.baidu.com/aistudio/projectdetail/697227

【API文档】
https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/index_cn.html

【PaddlePaddle/hapi Github】
https://github.com/PaddlePaddle/hapi

【Github使用】
https://guides.github.com/activities/hello-world/



# 3.个人介绍
> 中南大学 机电工程学院 机械工程专业 2019级 研究生 雷钢

> 百度飞桨官方帮帮团成员

> Github地址：https://github.com/leigangblog

> B站：https://space.bilibili.com/53420969

来AI Studio互关吧，等你哦~ https://aistudio.baidu.com/aistudio/personalcenter/thirdview/118783
欢迎大家fork喜欢评论三连，感兴趣的朋友也可互相关注一下啊~
