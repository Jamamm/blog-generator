---
title: 关于HTML的一些知识点
date: 2017-11-10 23:35:43
tags:HTML
---
HTML（超文本标记语言——HyperText Markup Language）是构成Web世界的基石。它描述并定义了一个网页的内容。其他除HTML以外的技术则通常用来描述一个网页的表现／展示效果（CSS）或功能（JavaScript）。（参考网站：https://developer.mozilla.org/zh-CN/docs/Web/HTML
常用标签：a、form、input、button、h1、p、ul、ol、small、strong、div、span、kbd、video、audio、svg。除了了 div 和 span，其他标签都有默认样式。
form、h1、p、ul、ol、div的默认display为block
p标签的一个文本级标签，p里面只能放字体、图片、表单元素，其他的一律不能放。


1、iframe标签
  ● 它是用来在一个页面嵌套一个页面
  ● 用法 <iframe src="#"> </iframe>
  ● 例子：
 	<iframe name=xxx src="#" frameborder="0"> </iframe>
 <a target=xxx href="http://qq.com">腾讯</a>
 <a target=xxx href="http://baidu.com">百度</a>

 2、a标签  anchor“锚”
完整写法
<a href="#"  title=“悬停文本” target="_blank/_self/_parent/_top" > 链接内容</a> 

①关于target 
<a href="#" target="_blank"> *** </a> 	  在空白页面打开
<a href="#" target="_self"> *** </a>     	  在当前页面打开
<a href="#" target="_parent"> *** </a>	  在父级页面打开
<a href="#" target="_top"> *** </a>		  在祖先页面打开

②关于下载
<a href="#" download> 下载 </a>
（注：http中  content-type： application/octtet-stream）


③a标签的href到底能写什么？
1、<a href="qq.com"> 例子</a>
这样是不能打开的，会以为它是一个文件路径

2、<a href="xxx.html"> 例子 </a>
打开的是/xxx.html

3、<a href="?name=frank"> 例子</a>
不会报错

4、<a href="#123"> 例子</a>
表示一个页面锚点，不发请求，但是页面位置会有改变，会回到顶部。

5、<a href="javascript:alert(打印出来的话);"> 例子</a>
伪装协议
<a href="javascript:;"> 例子</a>
这样点了a标签页面就不会发生跳转，可以满足一些比较奇葩的需求。

④a标签跳转页面是HTTP  GET  请求
   form标签跳转页面是HTTP  POST  请求


3、form标签  上传内容
例子：
<form action="users" method="post">
<input type="text" name="username">
<input type="password" name="password">
<input type="submit" name="提交">
</form>


