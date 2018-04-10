---
title: Fiddler使用进程账户本地调试
time: 2018.04.10 19:49:52
layout: post
tags:
- Fiddler
excerpt: Fiddle的特殊使用，可以查看后台二次请求，并能跟踪服务端的报错信息.
---

## 功能
Fiddle的特殊使用，可以在Fiddler跟踪到服务端的报错，这个很方便查找问题。
详解：以前，我们在后台请求了一个地址，获取其返回的数据。但有时候请求失败了，页面上报出500的错误，而Fiddler又不能看到到底哪里出了错误，比较让人心塞。
经过以下的设置之后，我们对于后台的请求就有了一个清晰的认识，知道请求了哪些地址，以及返回的数据，如果出错，还可以跟踪到错误的原因等等，方便后续的调试。

## 操作方法
1. 在IIS中，设置应用程序池的标识为当前登录用户。在“4”的地方，点击右边的选择按钮，将当前登录用户添加进去即可。 
<p class="no-indent"><img class="full-img" src="{{ site.loadingImg }}" data-src="{{ site.url }}/img/post/2018-04-10-fiddler-debug-with-local-account-1.png" /></p>

2. 计算机管理中，将当前登录账户添加到IIS_IUSRS组中去。(启动计算机管理，运行-compmgmt.msc，即可启动)
<p class="no-indent"><img class="full-img" src="{{ site.loadingImg }}" data-src="{{ site.url }}/img/post/2018-04-10-fiddler-debug-with-local-account-2.png" /></p>

3. 效果如下所示：
<p class="no-indent"><img class="full-img" src="{{ site.loadingImg }}" data-src="{{ site.url }}/img/post/2018-04-10-fiddler-debug-with-local-account-3.png" /></p>

4. 其中红框标注的地方为后台请求的地址，下面的方框中显示的是请求地址返回的数据。
<p class="no-indent"><img class="full-img" src="{{ site.loadingImg }}" data-src="{{ site.url }}/img/post/2018-04-10-fiddler-debug-with-local-account-4.png" /></p>

