---
layout: "intro"
page_title: "Project Setup - Getting Started"
sidebar_current: "gettingstarted-projectsetup"
description: |-
  The first step in configuring any Vagrant project is to create a Vagrantfile.
---

# 项目创建

配置任何Vagrant项目的第一步是创建[Vagrantfile](/docs/vagrantfile/)。Vagrantfile的用途有两点：

1. 标记项目的跟目录。Vagrant中的许多配置选项与此根目录相关。

2. 描述运行项目所需的机器和资源类型，以及要安装的软件和您想要访问的软件。

Vagrant有一个内置命令行可以初始化一个目录以用来使用Vagrant: `vagrant init`。 为了本入门指南的目的，请在您的终端中输入：

```
$ mkdir vagrant_getting_started
$ cd vagrant_getting_started
$ vagrant init
```

这将在当前目录放置一个`Vagrantfile`。你可以看一下这个Vagrantfile，如果你想看的话，它里面写了一些注释和例子。
如果看起来很吓人，请不要害怕，我们会尽快修改它。

您也可以在预先存在的目录中运行`vagrant init`，以便为现有项目设置Vagrant。

如果您使用版本控制，Vagrantfile可以和您的项目一起提交到版本控制。这样，每个从事该项目的人都可以从Vagrant得到任何前期工作。

## 下一步

你已经成功创建了你的第一个项目环境。继续阅读以了解更多关于[Vagrant boxes](/intro/getting-started/boxes.html)。
