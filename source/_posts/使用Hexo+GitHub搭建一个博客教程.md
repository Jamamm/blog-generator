---
title: 使用Hexo+GitHub搭建一个博客教程
date: 2017-11-08 14:56:21
tags:
---
下面是简单的几个步骤：
一、写第一篇博客
1、准备工作：成功搭建了git环境
2、进入一个安全的目录，比如 cd ~/Desktop 或者 cd ~/Documents
3、在 GitHub 上新建一个空 repo，repo 名称是「你的用户名.github.io」（请将你的用户名替换成真正的用户名）
4、运行 npm install -g hexo-cli ，安装 Hexo
5、运行 hexo init myBlog
6、运行 cd myBlog
7、运行 npm i
8、运行 hexo new 开博大吉 ，（hexo new 文章标题）  你会看到一个 md 文件的路径
9、运行 start xxxxxxxxxxxxxxxxxxx.md  ，编辑这个 md 文件，内容自己写
10、运行 start _config.yml ，编辑网站配置
    把第 6 行的 title 改成你想要的名字
    把第 9 行的 author 改成你的大名
    把最后一行的 type 改成 type: git
    在最后一行，与 type 平齐，加上一行 repo: 仓库地址 （请将仓库地址改为「你的用户名.github.io」对应的仓库地址，仓库地址以 git@github.com: 开头你知道吧？不知道？不知道的话现在你知道了）
    第 4 步的 repo: 后面有个空格，不要眼瞎。
11、运行  npm install hexo-deployer-git --save ，安装 git 部署插件
12、运行  hexo deploy
13、进入「你的用户名.github.io」对应的 repo，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接

你现在应该看到了你的博客！比如我的：https://jamamm.github.io/
  
二、写第二篇博客
1、运行 hexo new 第二篇博客
2、复制显示的路径，使用 start 路径 来编辑它
3、运行 hexo generate
4、运行 hexo deploy
去看你的博客，应该能看到第二篇博客了

三、换主题
1、进入https://github.com/hexojs/hexo/wiki/Themes 上面有主题合集
随便找一个主题，进入主题的 GitHub 首页，比如我找的是 https://github.com/iissnan/hexo-theme-next
2、复制它的 SSH 地址或 HTTPS 地址，假设地址为 git@github.com:iissnan/hexo-theme-next.git
3、运行 cd themes  进入这个文件夹
4、运行 git clone git@github.com:iissnan/hexo-theme-next.git
5、运行 cd ..
6、打开这个文件，将 _config.yml 的第 75 行改为 theme: hexo-theme-next，保存
7、运行 hexo generate
8、运行 hexo deploy

等一分钟，然后刷新你的博客页面，你会看到一个新的外观。如果不喜欢这个主题，就回到第 1 步，重选一个主题。