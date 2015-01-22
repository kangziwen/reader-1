reader
======

### 基于智能手机的报纸阅读器

- 应用背景：
	- 老年人由于视力衰退，标题大，阅读没问题，但报道内容文字较小，阅读困难，如果有人帮他读他感兴趣的内容，这个问题就可以得到解决。
- 使用过程：
 	- 用智能手机拍下感兴趣的文字内容，然就可阅读该内容，并可存储（可选操作）
- 功能要求：
	- 阅读内容照相。
	- 感兴趣内容定位，每次拍下的图片除了感兴趣内容外，还会有其他一些东西，但一个新闻报道在报纸上有明显的分界线，利用这些分界线定位感兴趣内容。
	- OCR：将定位文字图像识别成文字。
	- TTS：将识别的文字朗读出来。
	- 简单方便的操作过程设计。（交互）
	
### 相关资料

- 示意图片：

	 ![image](http://epaper.southcn.com/nfdaily/page/1/2014-11/25/A03/20141125A03_brief.jpg)
- 轮廓提取：openCV
- OCR：Tesseract、ABBYY
- TTS：讯飞语音
- Server：LeanCloud


### 文献综述

- 老年人行为分析与产品无障碍设计策略
	- 本文分析了老年人身体机能、认知能力及特定行为方式的变化，提出了符合老年人使用的产品的无障碍设计策略：操作界面易读，产品功能精简，表示符号统一，使用舒适。该文为本产品界面的设计指明了方向。
- 基于用户体验的老年人智能手机APP界面交互设计研究
	- 本文通过分析大量的用户调查结果，站在用户体验与老年人需求结合的角度上研究了老年人智能手机APP界面设计的影响因素。通过老年人智能手机健康助手APP的界面设计实践这个例子，阐述了实施老年人智能手机APP的界面设计的基本架构和需遵循的原则：从用户出发制定需求列表，从产品出发制定功能列表，根据用户体验层面模型确定设计需求和功能。该文对本产品的界面交互与界面设计流程有很大的帮助。
- 基于 Android 的手机 OCR 识别技术设计与实现
	- 本文通过开发 OCR 日程提醒小秘书软件，详细介绍了 OCR 的工作原理以及在智能手机平台上使用 OCR 的方法。文中对OCR开发的要点和容易出错的点做了详细的说明，展示OCR 日程提醒小秘书软件使用的实际效果。对 OCR 开发有很大的帮助。
- 基于Android平台的手机OCR系统及其应用
	- 本文分析了Tesseract的工作流程与相关算法，并对比几种常见的二值化方法，对算法进行优化，以提高OCR识别的效果。通过开发手机OCR系统的应用，与TTS结合实现了文本朗读的功能。本产品的开发参考了该文的实践思路。
- 利用 OpenCV 实现在 Android 系统上的图像边缘检测
	- 本文详细介绍了如何在 Android 系统上利用 JNI 调用 OpenCV，采用 Android NDK 生成动态链接库，进行图像边缘检测。本产品的其中一个功能“定位感兴趣的内容”需要使用 openCV，在开发该功能时参考了该文的思路。 
- Java 核心技术
	- 本书从如何创建第一个Java程序开始，系统全面讲解Java语言的核心概念、语法、重要特性和开发方法，以及Java环境的配置和Eclipse开发软件的使用。此书适合 Java 初学者学习使用。
- 第一行代码:Android
	- 全书由浅入深、系统全面地讲解了Android软件开发的方方面面。包括开发环境配置，Android资源介绍，通信方式，UI组件，高级调试分析，安全性和权限。并结合实例如闹钟，地图，联系人等应用，让一个只懂JAVA的软件开发者成为一个有经验的Android开发者。


### 开题报告

- 选题背景和意义
	- 本课题为基于智能手机的报纸阅读器。老年人由于视力衰退，平时阅读报纸时，由于新闻标题一般较大，不戴眼镜的情况下阅读也没问题，但新闻内容文字较小，不戴眼镜直接阅读较为困难，只能看到该条新闻在报纸上的大体位置和新闻间的空白形成的外围轮廓。但新闻内容一般较长，长时间戴眼镜阅读文字会对老年人造成眼睛疲劳的状况，极其不舒服。此时如果有人或者使用软件能够帮助老人阅读其感兴趣的内容，这个问题就可以得到解决。
	- 近几年来，智能手机的迅猛发展给人们的生活带来极大的便利。但随着社会老龄化问题的日益严重，智能手机市场对老年人市场的投入却跟不上社会改变的步伐。目前提供给老年人使用的 App 不仅数量少，而且界面依旧停留在大按钮，大字体上，使用起来感觉极其粗糙，并没有针对老年人的特点和使用场景进行有针对性的设计和开发。结果就是这些 App 并没有真正解决老年人的某些痛点问题。
	- 在网上搜索“智能手机 报纸 阅读器”，得到的结果基本上是传统类型的新闻类 App，如网易新闻，凤凰新闻等。老年人一般有看纸质报纸新闻的习惯，传统型的新闻类 App 由于功能繁多，操作上对老年人来说还存在不少不便之处，反而不适合老年人使用。
	- 本课题选择Android平台作为开发平台，因其使用范围广，基数大，可使其适用性大大增加。老年人只需使用该 App 对所需要阅读的内容拍照，程序即会将选中的内容朗读出来，解决了老年人由于新闻正文字体较小而造成的阅读不便的问题。本 App 还提供了存储功能，用户可选择将之前阅读的内容缓存起来，便于下次使用。
	- 传统型的新闻类 App 对老年人来说使用成本过高，本课题基于智能手机的报纸阅读器可有效的改善老年人在阅读纸质报纸新闻时的体验，且学习成本较低，适用性较高。解决了老年人由于视力衰退导致的阅读报纸不便的问题，对于提升老年人的生活质量具有重要意义。
- 工作任务分析
	- 本课题的目标是开发一款基于智能手机的报纸阅读器，在于解决老年人由于视力衰退导致的阅读报纸不便的问题，并具备良好的实用性与用户体验。除基础的拍照-朗读功能外，还具有存储功能，可将之前阅读的内容存储在手机上，便于下一次使用。
	- 拍照：使用手机摄像头对目标内容进行拍摄。
	- 定位新闻内容：由于上一步所得到的图片中可能混入一些与目标内容无关的信息，需要对所得图片进行处理，根据新闻间的空白形成的外围轮廓进一步确定需要朗读的新闻内容，也提供用户手动选择的功能。
	- 文字识别：将上一步处理后的图片转变成文字。
	- 朗读：将上一步得到的文字朗读出来。
	- 存储：将相应的新闻跟音频存储在手机上，并提供删除与排序功能。
	- 本课题将分三个阶段完成。第一阶段完成基本的拍照，文字识别与朗读功能。第二阶段完成定位新闻内容功能。第三阶段完成存储功能。- 调研报告
	- 随着智能手机平台的普及与智能手机平台应用开发的普及，以 Android 系统为例，Android 应用开发也已经成为一项人人皆可以参与的事情。基于智能手机的报纸阅读器其本身核心部分开发难度并不太大，实现相应功能所需要的库都能找到使用。所以本课题更多的是对功能的整合和对操作即用户体验上的改善。
	- 在豌豆荚上搜“报纸 阅读器”，得到的应用有好几十款。《报纸阅读器》是由安致爱好者开发，能在手机上阅读近百份国外的新闻报纸。《扫描版报纸阅读器》可阅读电子版报纸。目前可阅读参考消息、环球时报。阅读时可对报纸自由缩放、拖拽。支持批量下载所有版面。《我读报》是北京掌发科技有限公司自主研发的一款集数字报刊订阅、新闻个性化定制、互动分享为一体的新一代数字报刊阅读服务系统。通过无线互联网发行500多家报刊，用户可以在手持终端阅读原版原式的报纸。“语音读报”功能，使用户能够“听报”；“拍拍读报”拍照报头即可订阅数字报刊。《优阅读报》是世纪科美和科讯数码共同推出的一款可以在手机上原貌阅读实体报纸的客户端产品。不仅可以在线阅读河北当地各大主流报纸，还可以实现下载阅读、内容搜索、书签、书架、内容转发等功能。
	- 可以看出，基于智能手机的报纸阅读器，具有强大的适用性，其本身集成了丰富的多媒体拓展。且手机软件购买费用低廉（大多数免费），可以随时升级更换，无需承担过大的经济风险。
	- 目前，市面上现存的报纸阅读器存在以下不足：不支持新闻朗读；操作界面复杂，不适合老年人使用；对报纸的支持数量有限。还存在很大的提升空间。
	- 当然，基于智能手机的报纸阅读器也存有一些问题：Android 手机硬件配置档次高低不同，一些低端手机的拍照质量较差，对文本识别造成一定的困难。
	
- 方案拟定与分析
	- 系统总体框架：基于智能手机的报纸阅读器
		- 拍照
		- 定位内容
		- 文字识别
		- 朗读
		- 存储
	- 拍照
		- Android 中调用照相功能有两种方法：一种是调用系统自带的 camera，能够用 Intent 直接开启；另一种是利用 SurfaceView，能够添加自己想要的功能。本课题使用前一种，因为使用自定义的方式开启相机在不同的手机系统中容易出现兼容性问题，且系统自带的 camera 在 UI 上要美观些，便于使用。
	- 定位内容
		- 使用 openCV 实现。通过新建一矩形区域对原图进行裁剪。由于 openCV 是由 C++ 编写，Android 可通过 JNI 调用 openCV 提供的接口，有三种方式可以实现：使用静态的 openCV 库；使用动态的 openCV 库；同时使用 Java 的 API 又使用 JNI 的接口的方式，此时编译时一般使用的是动态链接 openCV 库的方式。本课题使用第一种方法，这样打包出来的 App 体积较小。
	- 文字识别
		- 使用 Tesseract 实现。Tesseract 是用 C++ 实现的，从 3.0 版本开始支持对中文的识别，需要封装 Java API 用于 Android 平台的调用。本课题使用的是 Tesseract-two，其集成了图形处理工具 leptonica，非常方便使用。	- 朗读
		- 使用讯飞语音实现，支持多种方式发音。只需调用系统提供的 TextToSpeech 类并实现相应的 onInit ，onDestroy 等接口即可。
	- 存储
		- Android 系统一共提供了四种数据存储方式。分别是SharePreference、SQLite、Content Provider 和File。本课题使用 Content Provider，这是一种能实现所有应用程序共享的一种数据存储方式，音频，视频，图片和通讯录通常使用该方式存储。每个Content Provider都会对外提供一个公共的URI（包装成Uri对象），如果应用程序有数据需要共享时，就需要使用Content Provider为这些数据定义一个URI，然后其他的应用程序就通过Content Provider传入这个URI来对数据进行操作。- 论文提纲
	- 引言
		- 课题背景
		- 课题任务
		- 论文结构
	- 开发环境及相关技术
		- Android 简介
		- Android SDK
		- Android 平台开发语言
		- Android 开发IDE
		- 本章小结
	- 报纸阅读器的需求分析
		- 业务描述
		- 业务处理流程
		- 客户需求分析
		- 本章小结
	- 报纸阅读器的功能设计
		- 客户端业务流程
		- UI组件布局
		- 拍照
		- 定位内容
		- 文字识别
		- 朗读文字
		- 存储内容
		- 本章小结
	- 报纸阅读器的实现
		- 项目开发软硬件平台
		- 项目创建
		- 软件功能架构
		- 软件功能实现
		- 本章小结
	- 结束语
		- 论文工作总结
		- 展望
	- 参考文献
	- 致谢
- 实施计划
	- 3.1——4.1：完成1、2、3章内容
	- 4.1——5.15：完成4、5章内容
	- 5.15——答辩：完成6章内容
- 参考文献
	- 王秋惠，老年人行为分析与产品无障碍设计策略[J].北京理工大学学报(社会科学版)，2009，11(1)，57-61
	- 彭佳，基于用户体验的老年人智能手机APP界面交互设计研究[D]. 上海:华东理工大学，2014
	- 朱怀中，基于 Android 的手机 OCR 识别技术设计与实现[J].电子科技，2012，25(9)，45-51
	- 桂杨，基于Android平台的手机OCR系统及其应用[D]. 南京:东南大学，2014
	- 杨平，利用 OpenCV 实现在 Android 系统上的图像边缘检测[J].计算机与数字工程，2014，42(7)，1254-1256
	- Cay S. Horstmann,Gary Cornell. Java核心技术(卷1):基础知识(原书第9版)[M]. 机械工业出版社, 2014.
	- 郭霖. 第一行代码:Android[M]. 人民邮电出版社, 2014.
	- 李林芳，基于目标导向的老年人智能手机界面设计研究[D]. 江苏:江南大学，2013
	- 余佳,黄智超,蒋端保,梁治峰,杨兵,帖军，基于Android图片文字朗读软件的盲人电子眼[J].软件导刊，2012，11(8)，96-98
	- 李松柏，浅析android平台图像处理应用[J].电子世界，2013，18，501	
	
### 外文翻译

- 外文名：An Approach towards text messaging to voice message for Smart Android phone
- 中文名：一种在安卓智能手机上将文本消息转换为语音消息的方法
- 摘要
	- 这里有几个将语音消息转换为文本消息的应用程序实现的研究结果。由于发明了语音识别系统，近几年开发者已经设计和开发了针对移动设备的且具有通用性的自动阅读机等产品。由于问题的复杂性和语音信号和声音的变化而没有用在计算机和电子领域。现在手机被广泛使用，短信是其中一个重要的应用。在本文中，我们试图反过来从文本消息到语音消息。我们认为，这种努力将有助于实现与各种通信设备之间的接口。我们可以处理文字和顺利地合成语音信号。在本文中，我们获取了各种语言以文本消息转换成语音信息的样本。这种类型的应用程序可以作为从文本消息到语音消息的两个不同的实体之间沟通的桥梁。本文介绍了三种不同的层次。
	- 第一个层次是将英语语音转换为英语文本。这种层次的类型可以用于帮助盲人。
	- 第二个层次是转换为当地语言。这种层次的类型有益于不懂英文的人。
	- 第三个层次是与移动设备相关联的（例如Android平台），每个人都可以各取所需。
- 关键词：SMS；语音采集；HMM；基于 HMM 的识别；安卓系统；DVM；语音识别；NLP；TTS
- 介绍
	- 在今天的生活中，移动设备已经成为我们每天的必修部分，我们中的许多人需要随时随地打电话或者发短信。当他们不能做这些事的时候，他们中的许多人需要他们的手机。在移动的时候，做饭的事故可能会因为此活动而发生，因此一个可支持移动设计的语音到文本转换器用来避免发生这种意外。语音到文本转换的研究是从20世纪70年代开始的，在音位到字形转换的第一个实验中，是由音素串分割成单词的。这项工作被再次延伸到从速记到字形的转换。语音消息正在逐步降低文本消息的重要性，因为它在烹饪和驾驶时间能更安全的使用。本文介绍了有关的讲话文本转换为短信应用的想法。该软件允许用户发送短信，而无需使用键盘来拼写单词。现在让我们的重点转向短消息系统：这是手机短信服务组件，它使用标准通信协议，使短信能够在移动电话设备之间传送。短信是世界上最广泛使用的数据的应用程序，在全球有24亿活跃用户，占所有移动电话用户的74％[1]。智能手机为用户提供了增强的方法来使用自己的手机，但互动的最自然的方式依然是使用语音来进行交互。智能手机市场提供了许多与语音识别相关的应用程序。谷歌语音操作，最近iPhone的Siri的都是使用语音来控制移动电话：如给企业和联系人打电话发送短信和电子邮件，听音乐，浏览网页，并完成共同的任务。两着都需要连接到网络来进行相关的请求，且大多数手机在4G网络中能够比3G跑得更快。还有可用性的问题，语音操作都可以在Android 2.2以上的设备使用，但Siri仅适用于iPhone4S。Siri的优点是，它可以作用于各种各样的短语和请求，并能够理解和从自然语言学习，而谷歌的语音操作，仅能通过使用特定语音命令仅操作。在这项工作中，我们已经开发了使用谷歌语音识别引擎来发送短信的应用程序。这个应用的主要目的是让用户输入语音信息，然后发送语音消息作为所需的文本信息[2]。

