# 翁家翌（Jiayi Weng）

清华大学计算机系，本科生

[wengjy16@mails.tsinghua.edu.cn](mailto:wengjy16@mails.tsinghua.edu.cn)

## 教育

- **2016 -**，清华大学计算机科学与技术系，本科生；GPA：3.50/4.00（排名15%），[详细](/cv/courses_zh.html)
- **2013 - 2016**，福建省福州第一中学

## 个人奖项

| 年份 | 奖项                                                         | 链接                                                         |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 2017 | 清华之友——广药集团奖学金                                     |                                                              |
| 2017 | 第9次CCF软件能力认证（CSP认证），470/500（全国最高分）       | [成绩单](http://cspro.org/lead/dformsys/application/ccf/pdf/201708506634.pdf) |
| 2016 | 清华大学第18届电子设计大赛，三等奖                           |                                                              |
| 2015 | 第32届全国青少年信息学奥林匹克竞赛（NOI2015），三等奖（铜牌） | [获奖名单](http://history.ccf.org.cn/resources/2567814757332/news/NOI2015%E8%8E%B7%E5%A5%96%E5%90%8D%E5%8D%952015-12-25-10_52_58.htm) |
| 2015 | 第27届国际信息学奥林匹克中国队选拔赛暨全国信息学奥林匹克精英赛（CTSC2015），银牌 | [获奖名单](http://www.noi.cn/noi-news/huojiang/666-ccf-ctsc2015) |
| 2015 | 第九届亚洲和太平洋地区信息学奥林匹克中国赛区（APIO2015），银牌 | [获奖名单](http://www.noi.cn/noi-news/huojiang/667-apio2015) |
| 2015 | 2015 年全国青少年信息学奥林匹克冬令营（WC2015），二等奖      | [获奖名单](http://download.noi.cn/T/2015/NOI2015dly.htm)     |

## 文章

Shihong Song, **Jiayi Weng**, Hang Su, Dong Yan, Jun Zhu   [**Playing FPS Game with Environment-aware Hierarchical Reinforcement Learning**](/cv/viz2018.html)   submitted to AAAI 2019 (under review)

**Jiayi Weng**, Tsung-Yi Ho, Weiqing Ji, Peng Liu, Mengdi Bao, Hailong Yao   [**URBER: Ultrafast Rule-Based Escape Routing Method for Large-Scale Sample Delivery Biochips**](/cv/urber.html)   submitted to TCAD (in minor revision)

## 竞赛

### Visual Doom AI Competition at [CIG2018](https://project.dke.maastrichtuniversity.nl/cig2018/) Singleplayer Track (1), Winner

《毁灭战士 Doom》是1993 年推出的 FPS（First Person Shooter，第一人称射击）类游戏，该游戏是 AI 研究热门试验场。2016 年，基于游戏的 ViZDoom AI 竞赛诞生，研究能获取原始视觉信息的强化学习技术，因其高挑战性吸引众多顶级实验室，如 2016 年冠军 Facebook FAIR（Track 1）和英特尔（Track 2）、2017 年冠军 Marvin（Track 1）和卡耐基梅隆大学（Track 2）。

ViZDoom 2018 Track 1 是AI单人闯关模式，考核标准是最短时间内闯最多的关口。与以往经典的死亡竞赛不同，需要 AI 能同时完成探索路径、收集装备、躲避陷阱、杀死怪物、寻找出口等诸多复杂任务，对 AI 的任务理解和环境认知能力要求极高。在 53 个国际参赛团提交的 204 个机器人中，只有 6 个团队实现了有意义的闯关。

针对该复杂任务，我们团队提出了环境信息引导的分层强化学习技术，在对环境信息有效感知基础上，融合环境反馈和强化学习的奖励信号，引导分层强化学习训练，使得 AI 闯关表现优异，预赛中以绝对优势保持第一，直至决赛锁定冠军。

链接：[官方比赛结果](http://vizdoom.cs.put.edu.pl/competition-cig-2018/competition-results)，[中文媒体报道](https://www.jiqizhixin.com/articles/2018-08-23-12)。

## 项目

### 课程项目

- 真实感物体渲染（实现了路径追踪(Path Tracing)、渐进式光子映射(PPM)、随机渐进式光子映射(SPPM)等算法，渲染包含Bezier曲面的三维模型，被评为优秀大作业）：[代码](https://github.com/Trinkle23897/Computational-Graphics-THU-2018) - 计算机图形学课程
- 用一个自己设计的算法实现的多点对的逃逸布线路径寻找算法：[演示](https://trinkle23897.github.io/demo.html) - 面向对象程序设计基础课程
- 数独游戏，用Qt C++实现（被评为优秀大作业）：[代码](https://github.com/Trinkle23897/sudoku-qt5)
- C/S结构的在线国际跳棋游戏，用Qt C++实现：[代码](https://github.com/Trinkle23897/draughts-qt5)
- 基于Android的简易新闻阅读器：[代码](https://github.com/Trinkle23897/simple-news-android-app) - Java课程大作业
- 维基百科人物信息检索系统，用Python（Django）实现：[代码](https://github.com/Trinkle23897/list_of_people)


### 实习项目

#### 快速多帧降噪 - AI-based ISP Pipeline

在暗光、逆光等场景下，摄影设备采集的图像经过传统的图像处理模块(ISP Pipeline)之后会产生十分明显的颗粒噪点，对画质产生不良影响，甚至会降低后端神经网络处理任务的性能：比如在安防领域，夜晚场景下视频监控中的噪点会极大地降低人脸识别的准确度。因此图像降噪对于ISP而言是十分重要的一环。

之前的文献提出了一些使用神经网络进行空域降噪的方法，效果要明显优于传统降噪方法（e.g. NLM, BM3D, VBM4D），但是由于速度原因，如视频监控要求对于**全分辨率图像**至少30fps的处理速度，无法直接应用到工业界。

我设计了一个基于时域+空域的降噪网络，用8张连续拍摄的12M像素级别的图片（e.g. 4032*3024）作为输入，能在GTX1060上~70ms的时间内得出降噪结果，速度要远远快于之前的所有方法，并且降噪质量要明显优于只使用空域降噪的一些方法。由于实习协议，代码尚未公开。

## 实习

- 2018.3 - 2018.7  北京市商汤科技开发有限公司，前端交互计算部门，见习研究员，[公司网站](https://www.sensetime.com/)

## 命题

我参与过若干场次信息学比赛的命题，包括中国国家队集训（CTT）、清华大学优秀高中生信息学夏季体验营（THUSC）以及清华大学程序设计竞赛暨高校邀请赛（THUPC）等比赛。

| 比赛       | 名称           | 链接                                |
| ---------- | -------------- | ----------------------------------- |
| THUPC 2018   | 赛艇   | [题目](https://loj.ac/problem/6388) |
| THUPC 2018   | 密码学第三次小作业   | [题目](https://loj.ac/problem/6392) |
| CTT 2017   | 简单数据结构   | [题目](https://loj.ac/problem/2326) |
| THUSCU 2016 | 工资         | [题目仓库](https://git.thusaac.org/publish/THUSCU2017/tree/master/day1/wage) |
| THUSC 2016 | 杜老师         | 尚未公开 |
| THUSC 2016 | 宇宙广播       | 尚未公开 |
| CTT 2016   | 如何优雅地求和 | [题目](http://uoj.ac/problem/269)   |


## 其他

- 熟悉C、C++、Python
- 了解Java、JavaScript、MATLAB、LaTeX
- 英语四级：575

*上次更新于2018年9月14日*

------