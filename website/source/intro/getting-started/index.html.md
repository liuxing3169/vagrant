---
layout: "intro"
page_title: "Getting Started"
sidebar_current: "gettingstarted"
description: |-
  The Vagrant getting started guide will walk you through your first
  Vagrant project, and show off the basics of the major features Vagrant
  has to offer.
---

# 开始使用

Vagrant入门指南将引导你走过你的第一个Vagrant项目，并展示Vagrant提供的主要功能的基本用法。

如果你对于Vagrant提供了什么感到好奇，你应该读一下["为什么使用Vagrant?"](/intro/index.html)。

开始使用向导会使用Vagrant和[VirtualBox](https://www.virtualbox.org),因为它是免费的，可以在各个主流平台上使用，被内置到Vagrant。
在通读了这个向导后，不要忘记Vagrant可以和[其他大多数提供者](/intro/getting-started/providers.html)一起工作。

在深入你的第一个项目之前，请[安装最新版本的Vagrant](/docs/installation/)。而且因为我们将会使用[VirtualBox](https://www.virtualbox.org) 作为开始向导的供应者，所以请先安装它。

<div class="alert alert-block alert-info">
  <strong>更多的读物?</strong> 如果你更喜欢阅读一本纸质书，你可能会对
  <a href="https://www.amazon.com/gp/product/1449335837/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1449335837&linkCode=as2&tag=vagrant-20" class="alert-link">
  Vagrant: Up and Running</a>感兴趣，这本书是由Vagrant的作者编写的，并由O'Reilly出版社出版。 
</div>

## 启动和运行

```
$ vagrant init hashicorp/precise64
$ vagrant up
```
在运行上面两条命令后，你将会拥有一个完整的在[VirtualBox](https://www.virtualbox.org)中运行Ubuntu 12.04 LTS 64-bit系统的虚拟机。
你可以通过`vagrant ssh`命令SSH进入这台机器，当你玩耍完后，你可以通过`vagrant destroy`命令结束这台虚拟机。

现在想象一下你曾经工作过的每一个项目都是可以这样简单的创建起来！通过Vagrant，`vagrant up` 就是在任何一个项目中你需要做的，
安装项目需要的每一个依赖，建立起网络或者同步文件夹，以便你可以继续工作从你自己舒适的电脑上。

这个向导剩余部分将会带领你建立起一个更完整的项目，涵盖Vagrant的更多功能。

## 下一步

你刚刚已经通过Vagrant创建了你的第一个虚拟环境。了解更多关于[项目创建](/intro/getting-started/project_setup.html).
