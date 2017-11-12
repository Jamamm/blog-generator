---
title: 关于HTML的一些知识点1
date: 2017-11-11 15:00:51
tags: HTML iframe标签 a标签 form标签
---
HTML（超文本标记语言——HyperText Markup Language）是构成Web世界的基石。它描述并定义了一个网页的内容。其他除HTML以外的技术则通常用来描述一个网页的表现／展示效果（CSS）或功能（JavaScript）。（参考网站：https://developer.mozilla.org/zh-CN/docs/Web/HTML
常用标签：a、form、input、button、h1、p、ul、ol、small、strong、div、span、kbd、video、audio、svg。除了了 div 和 span，其他标签都有默认样式。
form、h1、p、ul、ol、div的默认display为block
p标签的一个文本级标签，p里面只能放字体、图片、表单元素，其他的一律不能放。


1、iframe标签
  ● 它是用来在一个页面嵌套一个页面
  ● 用法 <pre> &lt;iframe src="#"&gt; &lt;/iframe&gt;  </pre> 
  ● 例子：
  <pre>
  &lt;iframe name=xxx src="#" frameborder="0"&gt;  &lt;/iframe&gt;
  &lt;a target=xxx href="http://qq.com"&gt; 腾讯  &lt;/a&gt;
  &lt;a target=xxx href="http://baidu.com"&gt; 百度  &lt;/a&gt;
  </pre>

 2、a标签  anchor“锚”
完整写法
<pre>
&lt;a href="#"  title=“悬停文本” target="_blank/_self/_parent/_top" &gt; 链接内容&lt;/a&gt; 
</pre>

①关于target 
<pre>
&lt;a href="#" target="_blank"&gt; *** &lt;/a&gt; 	  在空白页面打开
&lt;a href="#" target="_self"&gt; *** &lt;/a&gt;     	  在当前页面打开
&lt;a href="#" target="_parent"&gt; *** &lt;/a&gt;	  在父级页面打开
&lt;a href="#" target="_top"&gt; *** &lt;/a&gt;		  在祖先页面打开
</pre>

②关于下载
<pre>
&lt;a href="#" download&gt; 下载 &lt;/a&gt;
</pre>
（注：http中  content-type： application/octtet-stream）


③a标签的href到底能写什么？
<pre>
1、&lt;a href="qq.com"&gt; 例子&lt;/a&gt;
</pre>
这样是不能打开的，会以为它是一个文件路径

2、<pre>&lt;a href="xxx.html"&gt; 例子 &lt;/a&gt;</pre>
打开的是/xxx.html

3、<pre>&lt;a href="?name=frank"&gt; 例子&lt;/a&gt;</pre>
不会报错

4、<pre>&lt;a href="#123"&gt; 例子&lt;/a&gt;</pre>
表示一个页面锚点，不发请求，但是页面位置会有改变，会回到顶部。

5、<pre>&lt;a href="javascript:alert(打印出来的话);"&gt; 例子&lt;/a&gt; </pre>
伪装协议
<pre>
&lt;a href="javascript:;"&gt; 例子&lt;/a&gt;
</pre>
这样点了a标签页面就不会发生跳转，可以满足一些比较奇葩的需求。

④a标签跳转页面是HTTP  GET  请求
   form标签跳转页面是HTTP  POST  请求


3、form标签  上传内容
例子：
<pre>
&lt;form action="users" method="post"&gt;
&lt;input type="text" name="username"&gt;
&lt;input type="password" name="password"&gt;
&lt;input type="submit" name="提交"&gt;
&lt;/form&gt;
</pre>

