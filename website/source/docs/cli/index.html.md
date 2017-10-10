---
layout: "docs"
page_title: "命令行接口"
sidebar_current: "cli"
description: |-
  Almost all interaction with Vagrant is done via the command-line interface.
---

# 命令行接口

几乎所有和Vagrant的交互都可以通过命令行接口完成。

这些接口可以通过`vagrant`命令进行使用，它们是在安装Vagrant时自带的。
`vagrant`命令有很多子命令，如`vagrant up`, `vagrant destroy`,等等。

如果你单独的运行`vagrant`，帮助会列出所有可用的子命令。除此之外，你可以运行任意Vagrant命令带上`-h` 标记，以输出关于这个指定命令的帮助。
例如，试试运行`vagrant init -h`。该帮助将输出一个句子概要，该命令的作用以及命令接受的所有标志的列表。

通过阅读本网站左侧导航区域中可用的相应子部分，可以获得各种Vagrant命令的深度文档和用例。

您也可以查阅有关可用于以全局方式配置和控制Vagrant的环境变量的[文档](/docs/other/environmental-variables.html) 。
