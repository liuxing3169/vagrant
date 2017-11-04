---
layout: "docs"
page_title: "查找和使用盒子"
sidebar_current: "vagrant-cloud-boxes-using"
---

# 查找和使用盒子

HashiCorp的Vagrant Cloud的一个主要用例是能够轻松地找到可用于Vagrant的包含Vagrant环境所需技术的盒子。
我们让这件事变的相当的简单：

1. 去到[发现页面](https://vagrantcloud.com/discover),并搜索你想要的任何盒子。

1. 一旦你找到了一个盒子，点击它的名字并了解它的更多信息。

1. 当你准备使用它时，复制它的名字，如"hashicorp/precise64"并通过`vagrant init hashicorp/precise64`初始化你的Vagrant项目。
或者，如果你已经有一个创建好的Vagrant项目，修改Vagrantfile以使用此盒子：`config.vm.box = "hashicorp/precise64"`
