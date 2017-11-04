---
layout: "docs"
page_title: "盒子"
sidebar_current: "boxes"
description: |-
  Boxes are the package format for Vagrant environments. A box can be used by
  anyone on any platform that Vagrant supports to bring up an identical
  working environment.
---

# 盒子

盒子是Vagrant环境下的包装格式。一个盒子可以被用在Vagrant支持的任意平台上， 从而带给开发团队一个统一的工作环境。

`vagrant box`提供了管理盒子所用到的所有功能。你可以阅读[vagrant box](/docs/cli/box.html)命令的文档了解更多信息。

使用一个盒子最简单的方式时从[Vagrant盒子的公有可见目录](https://vagrantcloud.com/boxes/search)添加一个盒子。
你也可以填写和分享你自己定义的盒子到这个网站上。

盒子还支持版本化，因此团队的成员使用Vagrant可以轻松的更新基础盒子，创建盒子的人可以推送修复，而且这些修复会有效的进行传达。

您可以通过阅读此页面以及左侧导航栏中的子页面了解关于盒子的所有信息。

## 发现盒子

查找盒子的最简单的方法是查看[公共Vagrant盒子目录](https://vagrantcloud.com/boxes/search)，找到符合您使用的盒子。
目录包含了大多数主流的操作系统作为基础，以及使用LAMP堆栈，Ruby，Python等快速启动和运行的盒子。

公共目录中的盒子在多种不同的[提供者](/docs/providers/)上工作。无论你是使用Vagrant和VirtualBox, VMware, AWS, 等等，
你应该都可以找到你所需要的盒子。

从目录添加一个盒子是非常简单的。每一个盒子都像你介绍了如何添加它，但它们都遵从相同的格式：

```
$ vagrant box add USER/BOX
```

例如: `vagrant box add hashicorp/precise64`. 你可以通过`vagrant init hashicorp/precise64`快速地初始化一个Vagrant环境。

~> **命名空间不能保证盒子的权威!** 一个普遍的误解是如"ubuntu"这样的名称空间代表了Ubuntu盒子的权威空间。
这是不对的。在Vagrant云上的名称空间和GitHub上的名称空间非常相似，例如，就像GitHub的支持团队不能在其他人的代码仓库分配问题，
HashiCorp的支持团队不能帮助第三方发布盒子。

## 官方盒子

HashiCorp (Vagrant的制作者) 发布一个基础的Ubuntu 12.04(32 and 64-bit)盒子可用于少量的一些使用场景。
它是高度优化过的，体积非常小，包含了支持Virtualbox和VMware。你可以如下面的方式使用它：

```shell
$ vagrant init hashicorp/precise64
```

或者你可以更新你的`Vagrantfile` 如下：

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
end
```
对于其他用户，我们推荐[Bento boxes](https://vagrantcloud.com/bento)。Bento boxes是[开源](https://github.com/chef/bento)的并
为多数的提供者创建，包括VMware, Virtualbox,和Parallels。有多种操作系统和各种版本可用。

这里只有两种官方推荐的盒子集合。

~> **这通常是一种困惑**, 但是官方(制作Ubuntu操作系统的公司)发布盒子到到Vagrant云的"ubuntu"名称空间下。
这些盒子仅支持Virtualbox，并不为大多数用户提供理想的体验。如果你使用这些盒子时遇到问题，请尝试用Bento boxes替代。
