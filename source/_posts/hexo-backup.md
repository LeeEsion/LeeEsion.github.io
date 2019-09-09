---
title: hexo-backup
date: 2019-09-09 15:02:08
tags:hexo
categories: 教程
---

# 安装Hexo

在本地博客文件下右键点击`Git Bash Here`，然后输入`npm i hexo-cli -g`安装Hexo。

安装完后输入`hexo -v`验证是否安装成功。

（不需要）然后就要初始化我们的网站，输入`hexo init`初始化文件夹，接着输入`npm install`安装必备的组件。

# 创建新分支

在github博客仓库下新建一个分支`hexo` 。（不过在建立新分支前请确保仓库内已有`master`分支（Hexo本地建站后第一次上传时会自动生成），否则后期再添加`master`分支比较麻烦（请自行搜索`git`命令））

然后`git clone https://github.com/×××/×××.github.io  `到本地，把`.git`文件夹拿出来，放在博客根目录下。

然后在博客根目录下的git base输入`git checkout hexo`切换到`hexo`分支

在博客根目录下

```bash
git add .
git commit -m "Backup"
git push origin hexo
```

这样就备份完博客了且在Github上能看到两个分支(`master`和`hexo`)。

# 设置默认分支

在Github上你的github.io仓库中设置默认分支为`hexo`。这样有助于之后恢复博客。`master`分支时默认的博客静态页面分支，在之后恢复博客的时候并不需要。

# 个人备份习惯

个人而言习惯于先备份文件再生成博客。即先执行

```bash
git add .
git commit -m "Backup"
git push origin hexo
```

将博客备份完成，然后执行`hexo g -d`发布博客。

# 恢复博客

目前假设本地Hexo博客基础环境已经搭好

# 克隆项目到本地

输入下列命令克隆博客必须文件(`hexo`分支)

```bash
git clone https://github.com/×××/×××.github.io
```

# 恢复博客

在克隆的那个文件夹下输入如下命令恢复博客

```bash
npm install hexo-cli
npm install
npm install hexo-deployer-git
```

还要重新配置`github`和`coding`的公钥。

在此不需要执行`hexo init`（第一步的初始化文件夹）这条指令，因为不是从零搭建起新博客。



参考文章：

1、[超详细Hexo+Github博客搭建小白教程](https://godweiyang.com/2018/04/13/hexo-blog/#toc-heading-12)

2、[在Github上备份Hexo博客](https://lrscy.github.io/2018/01/26/Hexo-Github-Backup/)

3、[git 创建 .gitignore 文件](https://www.cnblogs.com/shangdawei/archive/2012/09/08/2676708.html)