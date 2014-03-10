---
title: 开始
layout: tutorial
---

这篇文章会介绍整个Revel安装过程。

#### 安装 Go

想用Revel，首先要[安装 Go](http://golang.org/doc/install)。

#### 配置 GOPATH 环境变量

如果你还没有创建一个 GOPATH 环境变量，需要马上做。 GOPATH
 是一个保存所有 Go 公共代码的目录。以下是设置步骤：

1. 创建一个目录： `mkdir ~/gocode`
2. 创建 GOPATH 环境变量以便 Go 知道它在哪： `export GOPATH=~/gocode`
3. 将 GOPATH 环境变量添加到自启动里，便于以后使用： `echo GOPATH=$GOPATH >> .bash_profile`

Go 安装完毕。

#### 安装 git 和 hg

`go get` 依赖于 Git 和 Mercurial 来下载代码。

* [Git安装教程](http://git-scm.com/book/en/Getting-Started-Installing-Git)
* [Mercurial安装教程](http://mercurial.selenic.com/wiki/Download)

#### 获取 Revel 框架

运行以下命令获取 Revel 框架：

	go get github.com/revel/revel

这个命令做了下面两件事：

* Go 使用 git 将仓库克隆到 `$GOPATH/src/github.com/revel/revel/`
* Go 查找仓库代码的所有依赖，并用同样的`go get`方法下载到 GOPATH  中。

*__注意：__ 如果你是从v0.8或更早的版本升级而来，请看 [v0.9.0 发行说明](https://github.com/revel/revel/releases/tag/v0.9.0) 获取更多的说明。*

#### 编译 Revel 命令行工具

Revel 命令行工具是一个创建、运行、打包 Revel 程序的工具。

使用 `go get` 命令安装它：


	go get github.com/revel/cmd/revel

然后，确保 $GOPATH/bin 目录在 PATH 环境变量中，以便你可以在任何地方运行 Revel 命令行工具。

	export PATH="$PATH:$GOPATH/bin"
	echo 'PATH="$PATH:$GOPATH/bin"' >> .bash_profile

最后，我们试试它是不是正常工作：

	$ revel help
	~
	~ revel! http://revel.github.io
	~
	usage: revel command [arguments]

	The commands are:

	    run         run a Revel application
	    new         create a skeleton Revel application
	    clean       clean a Revel application's temp files
	    package     package a Revel application (e.g. for deployment)

	Use "revel help [command]" for more information.

设置完毕。

**下一篇： [新建一个 Revel 程序](createapp.html)**
