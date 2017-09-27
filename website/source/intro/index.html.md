---
layout: "intro"
sidebar_current: "intro-home"
page_title: "Introduction"
description: |-
  Vagrant is a tool for building complete development environments. With an
  easy-to-use workflow and focus on automation, Vagrant lowers development
  environment setup time, increases development/production parity, and makes
  the "works on my machine" excuse a relic of the past.
---

# 介绍Vagrant


Vagrant是一个在单个工作流中用来创建和管理虚拟机环境的工具。通过一个简单易用的工作流程并聚焦在自动上。Vagrant通过易于使用的工作流程并专注于自动化，降低了开发环境设置时间，提高了生产平均水平，并使“我的机器上的作品”成为过去时。

如果你已经对Vagrant的基础非常熟悉，[文档](/docs/index.html)为所有可用的功能和内部结构提供了更好的参考。

## 为什么要用Vagrant?

Vagrant提供建立在工业标准的技术之上，由单一控制工作流程的易于配置，可复制，可移植的工作环境 ，最大限度地提高生产力和灵活性给你和你的团队。

要释放它的魔力，Vagrant站在巨人的肩膀上。机器是构建在VirtualBox,VMware,AWS,或者[一些其他的提供商](/docs/providers/)之上。然后，工业标准的[配置工具](/docs/provisioning/)如shell scripts,Chef,或者Puppet，可以自动安装和配置软件到虚拟机里。

### 对于开发者

如果你是一名**开发者**,Vagrant会隔离依赖和它们的配置在一个一次性的、一致的环境中，没有
牺牲您所使用的工具(编辑器，浏览器，调试器,等等)。一旦你或者其他人创建了一个[Vagrantfile](/docs/vagrantfile/)，你只需要`vagrant up`，然后你工作所需的一切都已经安装并配置好了。
你团队的其他成员可以从相同的配置创建他们自己的开发环境，所以不管你是在Linux，Mac OS X或者Windows下，你们团队的每一个成员都是在相同的环境，相同的依赖，所有配置都一致的方式下运行代码。对“在我的机器上运行没问题”的bug说再见。

### 对于运营者

如果你是一名**实施工程师**或**运维工程师**，Vagrant给你一个可丢弃的环境和一致的工作流给开发和测试基础设施管理脚本，你可以快速测试如脚本，Chef
cookbooks，Puppet模块，和更多使用如VirtualBox 或 VMware之类的本地虚拟化。然后，通过_相同的配置_，你可以在如AWS或RackSpace等远程云环境用_同样的工作流_测试这些脚本。
抛弃您的自定义脚本来回收EC2实例，停止为各种机器提供SSH提示，开始用Vagrant给你的生活带来理智。

### 对于设计者

如果你是**设计者**，Vagrant将会自动设置好一个web应用程序所需的一切必需条件，以便使你聚焦于你最擅长的部分：设计。
一旦开发者配置好Vagrant，你就不必再担心如何去重新运行起一个web应用程序。不需要再劳烦其他的开发者来帮助修复你的环境然后才能做你最擅长的事情。
仅仅需要做的是签出代码，然后运行`vagrant up`，然后开始设计。

### 对于每个人

Vagrant是为每个人设计的，它提供了一种简单，快速的方式来创建一个虚拟环境！
