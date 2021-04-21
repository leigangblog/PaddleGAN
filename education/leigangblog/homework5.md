# 1.图像超分客观题
### 1.1 单选题
**1. GAN在超分任务中的优势是（）**

A.GAN更容易训练

B.GAN可以获得更高的PSNR指标

C.GAN可以生成更多的细节

D.GAN可以构建更深的网络

参考答案：C


**2. RCAN中的（）结构可以用来自适应地重新缩放每个通道的特征。**


A.RIR（Residual In Residual）

B.CA（Channel Attention）

C.LSC（Long Skip Connection）

D.RG（Residual Group）

参考答案：B


**3. 下列哪一项不是SRGAN的创新（）**


A.SRGAN首次将GAN应用于图像超分辨率

B.SRGAN生成的图像更加符合人的视觉感官

C.SRGAN提出了感知损失

D.SRGAN提升了图像超分的PSNR指标

参考答案：D


**4. SRGAN训练生成器的Loss不包括（）**


A.L1 Loss

B.MSE Loss

C.VGG Loss

D.对抗Loss

参考答案：A


**5. 下列哪一项不是ESRGAN对SRGAN的改进（）**


A.生成器网络结构

B.判别起网络结构

C.对抗损失

D.感知损失

参考答案：B


**6. ESRGAN关于对SRGAN的网络结构改进，不包括（）**


A.加入attention机制

B.把Residual Block变为Residual in Residual Dense Block (RRDB）

C.对残差信息进行缩放

D.去掉所有的 BN 层

参考答案：A


**7. 下列关于ESRGAN网络差值的描述错误的是（）**


A.网络插值可以平衡解决客观评价指标与主观评价指标的矛盾

B.网络插值是为了解决基于GAN的方法有时会生成奇怪的纹理，而非GAN的方法总是缺失细节

C.网络插值可以获得高PSNR指标同时具有丰富细节的超分图像

D.网络插值就是将基于PSNR训练的网络参数和基于GAN训练的网络参数加权相加

参考答案：C


**8. 下列关于EDVR模型说法错误的是（）**

A.特征提取模块是为了抽取特征以方便后续实现相邻帧的特征级对齐

B.PCD模块采用了金字塔结构和可变形卷积

C.TSA模块使用了spatial attention和temporal attention

D.重构模块是采用了数个带有BN的Residual Block 串联

参考答案：D


### 1.2 多选题

**1. 视频超分一般包括以下哪些模块（）**


A.特征提取模块

B.对齐模块

C.融合模块

D.重构模块

参考答案：ABCD

**2. 老北京视频修复需要用到的模型有（）**

A.超分辨率模型

B.上色模型

C.补帧模型

D.图像翻译模型

参考答案：ABC

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
