# 1.PaddleGAN与飞桨GAN打卡营介绍
### 1.1 PaddleGAN介绍

飞桨生成对抗网络开发套件--<b>PaddleGAN</b>，为开发者提供经典及前沿的生成对抗网络高性能实现，并支撑开发者快速构建、训练及部署生成对抗网络，以供学术、娱乐及产业应用。

GAN--生成对抗网络，被“卷积网络之父”Yann LeCun（杨立昆）誉为「过去十年计算机科学领域最有趣的想法之一」，是近年来火遍全网，AI研究者最为关注的深度学习技术方向之一。

![](https://ai-studio-static-online.cdn.bcebos.com/a5b9d420f9e04bbb9ef155be55b3e52791d9832b9d5347ceb17feb76834f122d)


Github地址:https://github.com/PaddlePaddle/PaddleGAN

Gitee地址:https://gitee.com/PaddlePaddle/PaddleGAN

### 1.2 飞桨GAN打卡营介绍

生成对抗网络七日打卡营课程链接：https://aistudio.baidu.com/aistudio/course/introduce/16651

生成对抗网络七日打卡营所有课程需用到的项目地址：https://aistudio.baidu.com/aistudio/projectdetail/1807841

* 课程安排：
    4月15日 20：30~21：30：Day 1 GAN基础概念及应用介绍
    
    4月16日 20：30~21：30：Day 2 GAN的技术演进及人脸生成应用
    
    4月17日 20：30~21：30：Day 3 图像翻译及卡通画应用
    
    4月18日 20：30~21：30：Day 4 超分辨率及老视频修复
    
    4月19日 20：30~21：30：Day 5 动作迁移理论及实践
    
    4月20日 20：30~21：30：Day 6 Wav2lip唇形合成理论及趣味应用
    
    4月22日 19：00~20：00：Day 7 作业讲评与拓展提升

# 2.预习作业
### 2.1 本地安装飞桨，成功后运行测试代码并截图上传

**注意**：**<span style="color:red">作业必须在本地完成</span>**，不是在AIStudio进行操作。**<span style="color:red">该部分在总成绩占比10%</span>**，如遇到问题，请在群聊/讨论区进行询问，会有助教进行解答~

你需要做：

	1.安装最新版本PaddlePaddle(2.0.1)
安装文档：[https://paddlepaddle.org.cn/install/quick](https://paddlepaddle.org.cn/install/quick)
		
    2.本地安装成功,输入测试代码并截图
**提示**：安装完成后您可以使用 python 或 python3 进入python解释器，输入import paddle ，再输入 paddle.utils.run_check()

如果出现PaddlePaddle is installed successfully!，说明您已成功安装。

**注**：以下两个项目是1.多版本时候所写，大致内容是不变的，大家安装的时候请安装2.0.1版本~(CPU/GPU均可)

本地安装PaddlePaddle的常见错误：[https://aistudio.baidu.com/aistudio/projectdetail/697227](https://aistudio.baidu.com/aistudio/projectdetail/697227)

手把手教你 win10 安装Paddlepaddle-GPU：[https://aistudio.baidu.com/aistudio/projectdetail/696822](https://aistudio.baidu.com/aistudio/projectdetail/696822)

	3.上传截图(下方是上传流程)
![](https://ai-studio-static-online.cdn.bcebos.com/129200c3adcd419e9c46b8bfd79f383e80df13f413734a40b67abe9989279b29)

![](https://ai-studio-static-online.cdn.bcebos.com/36df9d0672624829ae867fea894c867bdb32519d43d24c5f913df11fc39202a6)

**######请在这里提交图片######** 
![](https://ai-studio-static-online.cdn.bcebos.com/63bd52ac92fc4c1e8bdc8a3973f19d46e0d477e5892b4014a2ea2a0a6d944d14)


### 2.2 提交作业
	1.点击左边版本菜单

![](https://ai-studio-static-online.cdn.bcebos.com/a71bc9f3165b4187be03b1bb37d5e566bb3fd8e01a824ff99a105e53e0ccdb5c)

	2.点击生成新版本

![](https://ai-studio-static-online.cdn.bcebos.com/326b77deb3164471b71de552ad249a467545890165eb40a989a43292aefa2968)

	3.输入版本名称点击生成即可

![](https://ai-studio-static-online.cdn.bcebos.com/d7a9917b326b4227929b168c9dc611ca7dbf8c1acec748ddb6d480a062092d15)

	4.进入课程选择你要提交的作业(忽略那个已删除~)
    
![](https://ai-studio-static-online.cdn.bcebos.com/5cc21ad39fc94264a98b4c53c3f3daddeaccf1ec0b0045a5983946f410e8bc6d)

	5.点击提交作业

![](https://ai-studio-static-online.cdn.bcebos.com/cf254279f6034bb5bb9ff7194ffce8bad4be9f4e1bbc4afb9c42d83c83aaafb9)

	6.择你需要提交的版本
    
![](https://ai-studio-static-online.cdn.bcebos.com/f0e34a2da6fc4719af851e6365165396538caffd5dcc45fe8243332281084510)

	7.提交完成这里会有显示~

![](https://ai-studio-static-online.cdn.bcebos.com/dd31f918e21e4d508f750c182b8e904474e526ed591640f0b08386ebebc7031c)



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
