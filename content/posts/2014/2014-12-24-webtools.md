+++
date = "2014-12-24T08:36:54"
draft = "false"
title = "移动端Web开发工具小汇之一"
tags = ["Cyber Life"]

+++
上周在北京听了一位大牛的内部分享，回来整理了一下手头现在移动端web开发的工具流。以下文字基本都是copy官方说明。

//部分才是我的补充。一切工具和工作流都是围绕【产品】→【设计】→【前端】→【测试】→【交付】这个体系循环进行的。
![图片1.png](http://upload-images.jianshu.io/upload_images/22841-8e04e675fee523c5.png)

![GitHub.png](http://upload-images.jianshu.io/upload_images/22841-fb9153ce4237ad27.png)
GitHub 存放使用Git版本控制的软件代码和内容项目。除了允许个人和组织创建和访问代码库以外，它也提供了一些方便社会化软件开发的功能，包括允许用户跟踪其他用户、组织、软件库的动态，对软件代码的改动和 bug 提出评论等。GitHub也提供了图表功能，用于显示开发者们怎样在代码库上工作以及软件的开发活跃程度。
//这个不废话了。

![smacss.com.png](http://upload-images.jianshu.io/upload_images/22841-87ec6e3fff328755.png)
SMACSS（Scalable & Modular Architecture for CSS），其主要原则有3条：Categorizing CSS Rules（为css分类）
•	Naming Rules（命名规则）
•	Minimizing the Depth of Applicability（最小化适配深度）
SMACSS认为css有5个类别，分别是：
•	Base (基本)
•	Layout（布局）
•	Module (模块)
•	State (状态)
•	Theme (主题)

![图片3.png](http://upload-images.jianshu.io/upload_images/22841-7453d05f7a8b5695.png)
参考文档：https://nicolas.steinmetz.fr/web-enthusiasts/post/2013/06/05/Atomic-design
http://bradfrost.com/blog/post/atomic-web-design/
http://www.slideshare.net/bradfrostweb/atomic-design?ref=http%253A%252F%252Fbradfrost.com%252Fblog%252Fpost%252Fatomic-web-design%252F
![Atomic_m.jpg](http://upload-images.jianshu.io/upload_images/22841-9fd0467cce60fc89.jpg)
//Atomic工作流优化和革新了设计师面对页面时的视觉，创作不再是一个个图层，而是按照原子→分子→生物→模板→网页的构架模式一步步展开的。
 

 ![yeomanjs.org.png](http://upload-images.jianshu.io/upload_images/22841-f4e6666daaf63360.png)
Yeoman是Google的团队和外部贡献者团队合作开发的，目标是为开发者创建一个易用的工作流。
Yeoman主要有三部分组成：yo（脚手架工具）、grunt（构建工具）、bower（包管理器）。这三个工具是分别独立开发的，但是需要配合使用，来实现我们高效的工作流模式。
•	Yo 搭建新应用的脚手架，编写你的Grunt配置并且安装你有可能在构建中需要的相关的Grunt任务。
•	Grunt 被用来构建，预览以及测试你的项目，感谢来自那些由Yeoman团队和grunt-contrib所管理的任务的帮助。
•	Bower 被用来进行依赖管理，所以你不再需要手动的下载和管理你的脚本了。
//有些部分，比如Grunt现在看来已经过时或不适应高度碎片化的移动端web开发了，但工具控建议至少用它们度过你工作成长期的一个阶段。

![gruntjs.com.png](http://upload-images.jianshu.io/upload_images/22841-dba7f1ab98757782.png)
 http://gruntjs.com/ http://www.gruntjs.org/
Grunt是一个自动化的项目构建工具，如果需要重复的执行像压缩、编译、单元测试，代码检查以及打包发布的任务. 那么你可以使用Grunt来处理这些任务, 你所需要做的只是配置好Grunt，这样能很大程度的简化工作。

![smacss.com.png](http://upload-images.jianshu.io/upload_images/22841-f8888555dedeaafe.png)
Bower 基于nodejs的模块化思想，把功能分散到各个模块中，让模块和模块之间存在联系，通过 Bower 来管理模块间的这种联系。
包管理工具一般有以下的功能：
•	注册机制：每个包需要确定一个唯一的 ID 使得搜索和下载的时候能够正确匹配，所以包管理工具需要维护注册信息，可以依赖其他平台。
•	文件存储：确定文件存放的位置，下载的时候可以找到，当然这个地址在网络上是可访问的。
•	上传下载：这是工具的主要功能，能提高包使用的便利性。比如想用 jquery 只需要 install 一下就可以了，不用到处找下载。上传并不是必备的，根据文件存储的位置而定，但需要有一定的机制保障。
•	依赖分析：这也是包管理工具主要解决的问题之一，既然包之间是有联系的，那么下载的时候就需要处理他们之间的依赖。下载一个包的时候也需要下载依赖的包。