# 1.GAN基础概念及应用介绍
### 1.1 生成对抗网络的概述
<b>生成对抗网络应用:</b>
* 数据生成
* 图片翻译
* 超分辨率
* 老视频修复
* 动作迁移
* 人脸动漫化
* 写实人像卡通化
* 照片动漫化
* 唇形同步

<b>生成对抗网络发展:</b>
* 14年提出以来，科研领域的关注度指数型增长
* 过去十年计算机科学领域最有趣的想法之一

<b>发展方向：</b>
* 网络结构
* 条件生成网络
* 图像翻译
* 归一化和限制
* 损失函数
* 评价指标

![](https://ai-studio-static-online.cdn.bcebos.com/6f4f877f1cca4fce96d8846d6848a09973603b045ad84ad4a01cdbae494e3a00)


<b>课程内容：</b>
* Day 1 GAN基础概念及应用介绍
* Day 2 GAN的技术演进及人脸生成应用
* Day 3 图像翻译及卡通画应用
* Day 4 超分辨率及老视频修复
* Day 5 动作迁移理论及实践
* Day 6 Wav2lip唇形合成理论及趣味应用
* Day 7 作业讲评与拓展提升

### 1.2 生成对抗网络的原理
判别器 与 生成器

![](https://ai-studio-static-online.cdn.bcebos.com/0d197fb279ab40959d3ae710f24697c1f40dacfc00234f04a89308cae05b4bde)


### 1.3 DCGAN的代码实践

![](https://ai-studio-static-online.cdn.bcebos.com/50ced6b12d164f3f9c2424f5bad9b3276ad1e5fc5ed640e1afbc7333bb54485b)


* DCGAN代码链接：https://aistudio.baidu.com/aistudio/projectdetail/1795662


### 1.4 PaddleGAN
飞桨生成对抗网络开发套件--<b>PaddleGAN</b>，为开发者提供经典及前沿的生成对抗网络高性能实现，并支撑开发者快速构建、训练及部署生成对抗网络，以供学术、娱乐及产业应用。

GAN--生成对抗网络，被“卷积网络之父”Yann LeCun（杨立昆）誉为「过去十年计算机科学领域最有趣的想法之一」，是近年来火遍全网，AI研究者最为关注的深度学习技术方向之一。

![](https://ai-studio-static-online.cdn.bcebos.com/93cec3b1d677431996f50a3772d8aaa7c2bd8394ea2140828947f67ef744665b)


* Github地址:https://github.com/PaddlePaddle/PaddleGAN

* Gitee地址:https://gitee.com/PaddlePaddle/PaddleGAN

# 2.第一课客观题
###  2.1 单选题
**1.（单选）下列哪一项是GAN的判别器的损失函数（）**

A. ![img](https://user-images.githubusercontent.com/48054808/115173831-b1315300-a0fa-11eb-9616-c8bd39dd74eb.png)

B. ![img](https://user-images.githubusercontent.com/48054808/115173874-c6a67d00-a0fa-11eb-8447-722a4d0993ca.png)

C. ![img](https://user-images.githubusercontent.com/48054808/115173903-d1f9a880-a0fa-11eb-90bd-7c143367444b.png)

D. ![img](https://user-images.githubusercontent.com/48054808/115173943-e178f180-a0fa-11eb-87ce-ba3e96e51572.png)

参考答案：C

**2.（单选）GAN和auto encoder结构本质的区别是（）**

A.  网络结构不同

B.  输入不同

C.  对数据集的要求不同

D. 损失函数不同

参考答案：D

### 2.2 多选题
**1.（多选）GAN的基础结构包括（）**

A.  生成器

B.  判别器

C.  编码器

D. 解码器

参考答案：AB

**2.（多选）GAN的应用包括（）**

A. 换脸  

B. 动作迁移

C. 图像翻译

D. 超分辨率

参考答案：ABCD

**3. （多选）生成对抗网络中的生成模型可以（）**

A.  输入噪声生成图像

B.  输入噪声和标签生成图像

C.  输入图像生成图像

D. 输入文字描述生成图像

参考答案：ABCD


**4.  （多选）下列关于GAN中对抗的描述正确的是（）**

A.  生成器与判别器互相对抗，在对抗中增强

B.  两个神经网络通过相互博弈的方式进行学习

C.  像警察与假钞，在对抗中增强警察的鉴别能力和小偷造假能力

D. 像自然界中捕食者与被捕食者在对抗中的进化

参考答案：ABCD

**5.  （多选）下列关于GAN的描述正确的是（）**

A.  生成网络希望Fake image的score尽可能的大

B.  生成网络希望Fake image的score尽可能的小

C.  判别网络希望Fake image的score尽可能的大

D. 判别网络希望Fake image的score尽可能的小

参考答案：AD

**6.  （多选）下列关于DCGAN的说法正确的有（）**

A.  使用卷积代替全连接层

B.  添加BatchNorm

C.  在生成器中使用Relu

D. 在判别器中使用Relu

参考答案：ABC


# 3.参考资料

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

# 4.个人介绍
> 中南大学 机电工程学院 机械工程专业 2019级 研究生 雷钢

> 百度飞桨官方帮帮团成员

> Github地址：https://github.com/leigangblog

> B站：https://space.bilibili.com/53420969

来AI Studio互关吧，等你哦~ https://aistudio.baidu.com/aistudio/personalcenter/thirdview/118783
欢迎大家fork喜欢评论三连，感兴趣的朋友也可互相关注一下啊~
