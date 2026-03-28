+++
date = "2014-12-25T08:36:54"
draft = "false"
title = "移动端Web开发工具小汇之二"
tags = ["Cyber Life"]

+++
这一篇讲讲WEB开发中设计师用到的工具，基本涉及了设计师工作的全流程。事实上，一个团队的做事风格很大程度上取决于leader的背景，核心是设计与核心是技术的团队，做事风格也不尽相同。在很多一流团队中，设计师起到了灵魂作用，因而也出现了“设计主导产品流”。在现在的团队中，对设计师的要求越来越多，一个既懂设计又懂代码的设计师是万千宠爱集于一身，很多优秀的设计师事实上也是将传统分工归于前端的事儿都给干了。因为在团队的有效沟通中，代码还原意义重大。

CSS Hat 设计代码输出自动化
![1408361839707.png](http://upload-images.jianshu.io/upload_images/22841-e73cfb2d5a4a8727.png)

CSS Hat 是一个可以一键将Photoshop图层转换为css代码的插件，用人话说，就是可以把SD效果图层转换成CSS3样式代码，包括阴影、发光、渐变，圆角之类的CSS3特效；可以随意设置你的背景颜色与不透明度。另外它的兼容性非常好，不但同时支持Windows与Mac，也能支持Photoshop cs4、CS5、CS6。当然价格也不便宜，$34.99刀，不过对于专业设计师来说，还是值得购买的，可以找你的leader报销。
另外现在一共是三顶帽子：CSSHat，PNGHat，IOSHat，打包价格还算实惠。

Belvedere 文件管理自动化工具
![belvedere-9.jpg](http://upload-images.jianshu.io/upload_images/22841-36e70146f1e79360.jpg)
一个粗心大意的设计师的电脑硬盘必定是惨不忍睹的，他自己绝逼找不到几个月前做出来的设计稿究竟存到哪里去了。Belvedere是一款挺老的软件，通过按照文件类型移动和分类文件、按创建日期自动删除文件、以及其他规则，使得文件管理工作会更有条理、更有效率。

Sikuli  屏幕操作自动化 
![1350141391.png](http://upload-images.jianshu.io/upload_images/22841-b339e19bb3759029.png)
一句话介绍就是“会截图就会自动化测试”。Sikuli(http://slides.sikuli.org/)基于 Jython 的脚本语言以及集成开发环境，使用者可利用屏幕截图直接引用 GUI 元素进行编程，完成交互操作。看图就明白了。
![image007.jpg](http://upload-images.jianshu.io/upload_images/22841-ee721860f1ce6079.jpg)
这里有篇详细攻略：http://www.ibm.com/developerworks/cn/opensource/os-cn-sikuli/

spritepad 雪碧图自动生成
![CSS3Logo_406A9E5E.jpg](http://upload-images.jianshu.io/upload_images/22841-42ac5de2cd963ff9.jpg)
Css Sprite是一种CSS图像合并技术，该方法是将小图标和背景图像合并到一张图片上，然后利用css的背景定位来显示需要显示的图片部分。因为Sprite正好是雪碧的英文商标，故俗称雪碧图。雪碧图技术将网站上用到的图片素材集合到一张单独的图片中，从而减少网站HTTP请求数量。不过，雪碧图使用CSS background和background-position属性渲染，也就是说图片是在CSS中定义，而非标签。来看一张典型的雪碧图：
![prev.png](http://upload-images.jianshu.io/upload_images/22841-3f039a550b0d86b0.png)
当然，初学者一定要谨记：雪碧图决不可滥用。否则，那将是一场灾难。我最早知道雪碧图技术，就是读到某大牛喷淘宝首页雪碧图用的有多糟糕的。
雪碧图生成工具有很多，选择趁手和靠谱的即可，比如http://wearekiss.com/spritepad 
或者 http://csssprites.com/
由于retina屏的普及，这篇大牛的文章也值得一读：http://www.toobug.net/article/css_image_sprites_on_retina_screen.html

Web设计师photoshop常用插件还可以看这篇文章 http://www.jiawin.com/photoshop-plugin-for-web-designers
