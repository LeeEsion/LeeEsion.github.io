---
title: 备份&恢复
date: 2019-09-09 11:55:29
tags: hexo
categories: 教程
---

# 基础软件安装

安装备份下/hexo的软件

```bash
Git-2.23.0-64-bit.exe #基础程序
node-v10.16.3-x64.msi #基础程序
Sublime Text 2.0.2a x64 Setup.exe #编辑json文件程序
typora-setup-x64.exe #编辑文章程序
```



# 安装Hexo

1、在 **blog** 根目录下 **git base here**

2、安装Hexo

```bash
npm i hexo-cli -g
```

3、验证Hexo是否安装成功

```bash
hexo -v
```

4、复制备份文件（如果已复制这一步就不需要）



# 连接Github与本地

1、在blog根目录下git base here

2、输入下列命令（双引号不能删）

```bash
git config --global user.name "Github用户名"
git config --global user.email "注册GitHub使用的地址"
```

3、生成密钥SSH key（双引号不能删）

```bash
ssh-keygen -t rsa -C "注册GitHub使用的地址"
```

4、打开[github](https://github.com/)，在头像下面点击**settings**，再点击**SSH and GPG keys**，新建一个**SSH**，名字随便。（先不要按确定）

5、在git base中输入

```bash
cat ~/.ssh/id_rsa.pub
```

6、将输出的内容复制到第四步那个框中，点击确定保存。

7、输入如下，如果出现我的名字，那就证明成功

```bash
ssh -T git@github.com
```

8、修改 **_config.yml** 文件，修改最后一行为（**repository**修改为你自己的**github**项目地址。）

```bash
deploy:
  type: git
  repository: https://github.com/godweiyang/godweiyang.github.io
  branch: master
```

9、更快的方法：将 **dropbox** 备份里的 **ssh** 文件直接复制到 **C:\Users\用户名\.ssh**

# 写、发布文章

1、输入以下，生成文章文件

```bash
hexo n <name>
```

2、编辑完后检验

```bash
hexo clean #清除缓存
hexo g #生成静态网页
hexo s #本地预览
hexo d #上传至github
```

3、快速的方法

```bash
hexo g -d #生成+上传
```

4、在blog根目录下git base here输入（必须在上传文章前输入）

```bash
export HEXO_ALGOLIA_INDEXING_KEY=我的Algolia的Search-Only API Key
```

在windows的cmd命令行输入

```bash
set HEXO_ALGOLIA_INDEXING_KEY=我的Algolia的Search-Only API Key
```

再

```bash
hexo clean
hexo algolia
```



参考文章：

1、[超详细Hexo+Github博客搭建小白教程](https://godweiyang.com/2018/04/13/hexo-blog/)

2、[hexo：(三)hexo Next 主题配置---补充---Algolia 搜索](https://chentging.github.io/2018/05/16/hexo：（三）hexo-Next-主题配置-补充-Algolia-搜索)



