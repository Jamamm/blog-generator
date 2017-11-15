---
title: GitHub-Pages重新绑定域名踩的坑
date: 2017-11-15 11:31:56
tags: GitHub-Pages
---
<strong>总结：域名重新绑定GitHub-Pages的时候一定要把之前绑定的那个文件CNAME   git push掉！</strong>

过程：
新建了一个GitHub账号，想重新发布一个博客，于是按照步骤弄，前面都没问题，然后到了绑定域名这一步，怎么绑定都不行。
之前的域名绑定的还是之前的那个博客页面。我心想那我把之前的删了，这样你总不能再跳去了吧。然后我再重新绑定这个。
然后我就去把那个文件删了，文件都没了，总好了吧？
回来一看，怎么还在？
。。。
不管了账号注销掉
。。。
还在，无语了
只跑去官网看，结果发现。。
<blockquote><p>
“To remove the custom domain from a different GitHub Pages site repository you own, you can add a different custom domain to your GitHub Pages site or just remove your old custom domain.

If you don't own the repository that contains the CNAME file with your custom domain, try to contact the owner and ask them to update their custom domain. If you're unsure which repository contains the CNAME file with your custom domain, contact GitHub Support.”
</p></blockquote>

mdzz，这下惨了，只好乖乖去找客服
客服如是说
<blockquote><p>
“Hello Jam,

A quick way we can verify your ownership of the domain and delete those CNAME files would be for you to add a TXT record to your domain.

When you create the TXT record, please include the following value:

github-verification=F4ksxzuAhh3c4j2UVN6fhrsnneRWT9fnTHVAw2EP

If you need a name for the record, please use "@".

After that's been added and DNS has propagated, you can run the following command to verify the changes have been made:

dig example.com TXT

The results of that command should look something like:

› dig example.com TXT
;example.com. IN TXT
example.com. 3455 IN TXT "github-verification=F4ksxzuAhh3c4j2UVN6fhrsnneRWT9fnTHVAw2EP"

Please let me know once you've done this so we can verify and clear that domain, or if you have any questions about this verification process.

Shawna”</p></blockquote>

客服给的解决办法还是在Linux上的命令，只好又安装了一个BIND
步骤：
第一步;下载BIND 工具解压，打开BINDInstall.exe文件，勾选tools only,安装目录建议默认C盘路径，点击install安装，安装完毕后配置变量环境。
第二步：配置环境
点击桌面我的电脑-属性-高级系统变量-高级-环境变量-path-双击打开path，在后面添加如下路径“   ;C:\Program Files\ISC BIND 9\bin ”前面分号隔开，保存！
第三步：在运行输入cmd命令，回车在弹出命令窗口输入dig www.baidu.com +trace，查看能否正常dig.

按照步骤操作
然后再联系客服终于解决了。

<strong>原因：
之前的那个CNAME文件在GitHub服务器上还在生效，所以光是删除掉是不够的，必须git push覆盖掉。</strong>



好了，<a href="http://dengjian.space/">博客地址</a>

