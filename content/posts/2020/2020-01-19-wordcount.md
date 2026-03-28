+++
title = "Hugo成功添加字数统计和阅读时间"
date = 2020-01-19T23:08:11
draft = "false"
Tags = ["Cyber Life"]
+++
hugo还真是厉害！看到别人的blog里能显示”*本文共XXX字，阅读大约需要XX分钟*“，感觉挺高级的。话说阅读推荐时间最早还是在可能吧的公众号看到的。

仔细研究了一下，又看了一下*maupassant*的readme，发现hugo有函数支持这两个功能需求，于是动手搞了一下，一次成功！

## 需修改的页面地址
单篇文章修改，需要找到 *layouts > _default > single.html*

blog首页列表修改，需要找到 *layouts > index.html*

## 修改代码
在*single.html*找到

```html
 {{ if .Site.Params.busuanzi }}
        <div class="post-meta">
            <span id="busuanzi_container_page_pv">|<span id="busuanzi_value_page_pv"></span><span>
                    阅读 </span></span>|<span class="post-date">共{{ .WordCount }}字</span>，阅读约<span class="more-meta"> {{ .ReadingTime }} 分钟</span>
        </div>
        {{ end }}
```

在*index.html*找到
```html
<date class="post-meta meta-date">
            {{ .Date.Year }}年{{ printf "%d" .Date.Month }}月{{ .Date.Day }}日|<span class="post-date">共{{ .WordCount }}字</span>，阅读约<span class="more-meta"> {{ .ReadingTime }} 分钟</span>
        </date>
```
首页没有加阅读量是因为，第一加载有问题，只有第一条能加载出来，并且字段位置明显会有读取卡顿；第二是因为阅读量太低，就不好意思放了。