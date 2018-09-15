# Jiayi Weng (翁家翌)

[Chinese version / 中文版本](/cv/zh.html)

Undergraduate, Department of Computer Science and Technology, Tsinghua University, China

[wengjy16@mails.tsinghua.edu.cn](mailto:wengjy16@mails.tsinghua.edu.cn)

## Education

- **2016 -**, Undergraduate, Department of Computer Science and Technology, Tsinghua University, China; GPA：3.50/4.00 (ranking 15%) ,  [details](/cv/courses_en.html)
- **2013 - 2016**, Fuzhou No.1 High School

## Personal Award

| Year | Event                                                        | Link                                                         |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 2017 | Friend of Tsinghua, Guangzhou Pharmaceutical Holdings Limited Scholarship |                                                              |
| 2017 | 11th CCF Computer Software Certification, Passed with highest score | [Transcript (in Chinese)](/pdf/csptranscript.pdf)            |
| 2016 | 18th annual Electronic Design Competition in Tsinghua University, Third prize |                                                              |
| 2015 | 32nd National Olympiad in Informatics (NOI2015), Third prize (bronze medal) | [Winners (in Chinese)](http://history.ccf.org.cn/resources/2567814757332/news/NOI2015%E8%8E%B7%E5%A5%96%E5%90%8D%E5%8D%952015-12-25-10_52_58.htm) |
| 2015 | The Chinese Team Selection Contest for IOI 2015 (CTSC2015), Second prize (silver medal) | [Winners (in Chinese)](http://www.noi.cn/noi-news/huojiang/666-ccf-ctsc2015) |
| 2015 | 9th  Asia-Pacific Informatics Olympiad (China District), Second prize (silver medal) | [Winners (in Chinese)](http://www.noi.cn/noi-news/huojiang/667-apio2015) |
| 2015 | 2015 National Youth Informatics Olympic Competition Winter Camp, Second prize | [Winners (in Chinese)](http://download.noi.cn/T/2015/NOI2015dly.htm) |

## Publication

Shihong Song\*, **Jiayi Weng**\*, Hang Su, Dong Yan, Jun Zhu   [**Playing FPS Game with Environment-aware Hierarchical Reinforcement Learning**](/cv/viz2018.html)   submitted to AAAI 2019 (under review)

**Jiayi Weng**, Tsung-Yi Ho, Weiqing Ji, Peng Liu, Mengdi Bao, Hailong Yao   [**URBER: Ultrafast Rule-Based Escape Routing Method for Large-Scale Sample Delivery Biochips**](/cv/urber.html)   submitted to TCAD (in minor revision)

## Competition

### Visual Doom AI Competition at [CIG2018](https://project.dke.maastrichtuniversity.nl/cig2018/) Singleplayer Track (1), Winner

Doom is the FPS (First Person Shooter) game launched in 1993, which is a popular test site for AI research. In 2016, the game-based ViZDoom AI competition was born, researching reinforcement learning techniques that capture raw visual information, and appealing to many top-level laboratories such as the 2016 champions Facebook FAIR (Track 1) and Intel (Track 2), 2017 Champion Marvin (Track 1) and Carnegie Mellon University (Track 2).

ViZDoom 2018 Track 1 is the single-player mode. The agent has to beat random generated levels as fast as possible. Different from the classic deathmatch scenario in the past, AI should complete many complicated tasks such as exploring, collecting resources, avoiding traps, killing monsters, and finding final goal. It requires extremely high task understanding and environmental awareness of AI. Of the 204 robots submitted by 53 international teams, only 6 teams achieved meaningful results.

Facing with this complex task, our team proposed a hierachical reinforcement learning method guided by environmental information. Based on the effective perception of environmental information, our method integrates environmental feedback and reinforcement learning reward signals, making AI excellent performance. We stayed first in absolute advantage in the preliminaries and won the championship in the final.

Here is the link for [the official results of the competition](http://vizdoom.cs.put.edu.pl/competition-cig-2018/competition-results) and [the news report of Chinese media](https://www.jiqizhixin.com/articles/2018-08-23-12).

## Project

### Course Project

- Realistic Image Rendering (implement Path Tracing algorithm, Progressive Photon Mapping (PPM) algorithm, Stochastic Progressive Photon Mapping (SPPM)algorithm, render 3D models with Bezier surface) : [Code](https://github.com/Trinkle23897/Computational-Graphics-THU-2018) - project for Computational Graphics course
- Super fast escape routing algorithm for multi-point pairs: [Demonstration](https://trinkle23897.github.io/demo.html) - project for fundamental OOP course
- Android-based simple news reader: [Code](https://github.com/Trinkle23897/simple-news-android-app) - Java Program Design and Training course
- Sudoku game, in Qt C++ (rated as excellent homework): [Code](https://github.com/Trinkle23897/sudoku-qt5)
- C/S Draughts game online, in Qt C++: [Code](https://github.com/Trinkle23897/draughts-qt5)
- Wikipedia Character Information Retrieval System, in Python with Django: [Code](https://github.com/Trinkle23897/list_of_people)


### Internship Project

#### Fast Multi-frame Noise Reduction - AI-based ISP Pipeline

In scenes of dark light and backlighting, image captured by photographic equipment will produce very obvious particle noise after passing through the traditional image processing pipeline (ISP Pipeline), which will adversely affect the image quality and even reduce the performance of the back-end neural network. For example, in video surveillance, noise in night scenes can greatly reduce the accuracy of face recognition. Therefore, image noise reduction is a very important part of ISP.

Previous papers have proposed some methods for spatial noise reduction using neural networks, which are significantly better than traditional noise reduction methods (e.g. NLM, BM3D, VBM4D), but due to speed reasons, such as video surveillance requires at least 30fps for **full resolution images** processing speed, it cannot be directly applied to the industry.

I designed a temporal & spatial domain based noise reduction network. Using 8 consecutive 12M pixel images (e.g. 4032*3024) as input, it can get the noise reduction result in the ~70ms time on one GTX1060. It is much faster than all previous methods, and the quality of noise reduction is significantly better than some methods that only use spatial noise reduction. Due to the internship agreement, the code has not been made public.

## Internship

- 2018.3 - 2018.7  SenseTime Inc., Department of Front-end Interactive Computing, Trainee Researcher, [Company Website](https://www.sensetime.com/)

## Problem-Setting

I have participated in problem-setting in several competitions of informatics, including Chinese Team Training (CTT), Tsinghua University Informatics Summer Camp for Excellent High School Student(THUSC), Tsinghua University Programming Competition and College Invitational Tournament (THUPC), etc.

| Contest | Task       | Link                            |
| ---------- | -------------- | ----------------------------------- |
| THUPC 2018   | Rowing | [Statement (in Chinese)](https://loj.ac/problem/6388) |
| THUPC 2018   | Third Cryptography Assignment | [Statement (in Chinese)](https://loj.ac/problem/6392) |
| CTT 2017   | Simple Data Structure | [Statement (in Chinese)](https://loj.ac/problem/2326) |
| THUSCU 2016 | Wage     | [Statement (in Chinese)](https://git.thusaac.org/publish/THUSCU2017/tree/master/day1/wage) |
| THUSC 2016 | Professor Du | Not yet public |
| THUSC 2016 | Cosmic Broadcast | Not yet public |
| CTT 2016   | How to Elegantly Sum Up | [Statement (in Chinese)](http://uoj.ac/problem/269) |

## Others

- Familiar with C, C++, Python
- Know Java, JavaScript, MATLAB, LaTeX
- CET-4: 575

*Last update on September 14, 2018*

------
