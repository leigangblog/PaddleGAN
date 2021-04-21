# 1.PaddleGAN实现物理学界大佬们合唱蚂蚁呀嘿

大家是不是玩「单人版」的蚂蚁呀嘿玩的很爽了呢？开始觉得不被满足？想要尝试与别人共舞「蚂蚁呀嘿」？想要的永远比拥有的更多？
![](https://ai-studio-static-online.cdn.bcebos.com/9e17be2b3a5f49ce90cc42d6f05d3638490dd4c09f3246ec9fec2a5e0b1d3112)

别慌！！[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)良心制作，在单人版被大家疯传之后，今天，[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)带来了多人版本的实现！！

**无需切换任何软件或安装包，手把手教你如何一键实现多人乱舞蚂蚁呀嘿**🤩🤩🤩

🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡

**🥳🥳 更绝的是，此次升级版无论是单人版还是多人版都可通用！🥳🥳**

🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡🧡💛🧡💛🧡

接下来，快和[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)一起来动手实现吧！

整个实现步骤还是老样子，分为三步：
1. 下载[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)
2. 运行First Order Motion命令
3. 配上音乐🎵

然后，优秀的你就拥有了一个顶级宝藏技能，一键实现多人蚂蚁呀嘿！！快去和你身边朋友炫耀吧~~

不要忘记给[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)点Star支持噢~~![](https://ai-studio-static-online.cdn.bcebos.com/dadbafa290874810bb3ff387f7c76ff250ff97aef1534e418b24ee0a4c97bee1)

## 1.1 效果预览

PaddleGAN施魔法前：

<div align='left'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/27f29d355e2a4a759c94d0475f9b53e6dcc6d765d55b486d9f9f542734b9f2be' width='600'/>
</div>

PaddleGAN施魔法后：

![](https://ai-studio-static-online.cdn.bcebos.com/1420a63130bb49f9ad00cc069d7568ac9696a4a818934071a0b3f9a7e986eeca)

**照片的历史背景介绍：**

1911年，第一届索尔维会议在布鲁塞尔召开，以后每3年举行一届。1927年，第五届索尔维会议在比利时布鲁塞尔召开了，因为发轫于这次会议的阿尔伯特·爱因斯坦与尼尔斯·玻尔两人的大辩论，这次索尔维峰会被冠之以“最著名”的称号。

一张汇聚了物理学界智慧之脑的“明星照”则成了这次会议的见证，数十个涵盖了众多分支的物理学家都留下了他们的身影，爱因斯坦、玻尔更是照片的灵魂人物。


## 1.2【多人版】动作迁移技术流程
整体流程分为三步：
1. 将照片中的多人脸使用人脸检测模型S3FD框出并抠出
2. 对抠出的人脸用First Order Motion进行脸部表情迁移
3. 将迁移好的人脸放回对应的原位置

**注意，由于人脸检测后，需要确定位置将人脸框出来并抠出，如果人脸太近，会框到除了其他的脸，导致效果较差，如下图**

<div align='center'>
  <img src='https://ai-studio-static-online.cdn.bcebos.com/b5d61c87269d4725ab194879343e56ce232b497ec6974f9e84881e4c199f6a40' width='300'/>
</div>

**所以尽量选取人脸间距较大的照片，同时，框的大小需要根据照片中人脸间距情况进行调节（参数--ratio）**

## 1.3 配置PaddleGAN环境


```python
# 从github上克隆PaddleGAN代码
%cd /home/aistudio/
#!git clone https://github.com/PaddlePaddle/PaddleGAN
# 如果已经存在PaddleGAN仓库，可注释下面两行代码，或者从下面安装所需安装包开始
!git clone https://gitee.com/paddlepaddle/PaddleGAN.git
!git checkout develop
```


```python
# 安装所需安装包
%cd PaddleGAN
!pip install -r requirements.txt
!pip install imageio-ffmpeg
%cd applications/
```

## 1.4 一键执行命令

大家可以上传自己准备的视频和图片，并在如下命令中的source_image参数和driving_video参数分别换成自己的图片和视频路径，然后运行如下命令，就可以完成动作表情迁移，程序运行成功后，会在ouput文件夹生成名为result.mp4的视频文件，该文件即为动作迁移后的视频。

同时，根据自己上传的照片中人脸的间距，

本项目中提供了原始图片和驱动视频供展示使用。具体的各参数使用说明如下
- driving_video: 驱动视频，视频中人物的表情动作作为待迁移的对象
- source_image: 原始图片，视频中人物的表情动作将迁移到该原始图片中的人物上
- relative: 指示程序中使用视频和图片中人物关键点的相对坐标还是绝对坐标，建议使用相对坐标，若使用绝对坐标，会导致迁移后人物扭曲变形
- adapt_scale: 根据关键点凸包自适应运动尺度
- ratio：将框出来的人脸贴回原图时的区域占宽高的比例，默认为0.4，范围为【0.4，0.5】

**本项目包括：**

* 蚂蚁呀嘿原视频：myyh.MP4

* unrevel视频：unravel.mp4 (注意大小写)


**下面代码任选一个即可**

由于照片中大佬比较多,一起合唱需要时间6-7min左右,请大家耐心等待


```python
# 合唱蚂蚁呀嘿
!export PYTHONPATH=$PYTHONPATH:/home/aistudio/PaddleGAN && python -u  tools/first-order-demo.py  --driving_video ~/work/myyh.MP4  --source_image ~/work/1.jpg --ratio 0.4 --relative --adapt_scale 
```


```python
# # 合唱unrevel
# !export PYTHONPATH=$PYTHONPATH:/home/aistudio/PaddleGAN && python -u  tools/first-order-demo.py  --driving_video ~/work/unravel.mp4  --source_image ~/work/1.jpg --ratio 0.4 --relative --adapt_scale 
```

## 1.5 使用moviepy为生成的视频加上音乐


```python
# add audio
!pip install moviepy
```


```python
#为生成的视频加上音乐
from moviepy.editor import *

videoclip_1 = VideoFileClip("/home/aistudio/work/myyh.MP4")  # 改为对应的驱动视频文件
videoclip_2 = VideoFileClip("./output/result.mp4")

audio_1 = videoclip_1.audio

videoclip_3 = videoclip_2.set_audio(audio_1)
videoclip_3.write_videofile("/home/aistudio/output/finalout.mp4", audio_codec="aac")
```

## 1.6 展示视频


```python
# display the output video
import cv2
import imageio
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.animation as animation
from IPython.display import HTML
import warnings

# video display function
def display(driving, fps, size=(8, 6)):
    fig = plt.figure(figsize=size)

    ims = []
    for i in range(len(driving)):
        cols = []
        cols.append(driving[i])

        im = plt.imshow(np.concatenate(cols, axis=1), animated=True)
        plt.axis('off')
        ims.append([im])

    video = animation.ArtistAnimation(fig, ims, interval=1000.0/fps, repeat_delay=1000)

    plt.close()
    return video
    
# 展示一下输入的视频, 如果视频太大，时间会非常久，可以跳过这个步骤
video_path = '/home/aistudio/output/finalout.mp4'
video_frames = imageio.mimread(video_path, memtest=False)

# 获得视频的原分辨率
cap = cv2.VideoCapture(video_path)
fps = cap.get(cv2.CAP_PROP_FPS)
    

HTML(display(video_frames, fps).to_html5_video())
```

## 1.7 多人版的动作迁移完成！

至此，多人版本的动作迁移就制作完成啦~

**大家快来动手尝试吧！记住，选择人物间距较大的合照效果更佳噢！**

当然，[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)的应用也不会止步于此，[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)还能提供各类不同的能力，包括**唇形合成（对嘴型）、视频/照片修复（上色、超分、插帧）、人脸动漫化、照片动漫化**等等！！一个比一个更厉害！

强烈鼓励大家玩起来，激发[PaddleGAN](https://github.com/PaddlePaddle/PaddleGAN)的潜能！

记得点个Star收藏噢~~
![](https://ai-studio-static-online.cdn.bcebos.com/e2a76e0a1b864259a11b3556dda2f6838503e476637a408f946b333d38438455)


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
