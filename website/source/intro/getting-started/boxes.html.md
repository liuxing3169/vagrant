---
layout: "intro"
page_title: "盒子 - 开始使用"
sidebar_current: "gettingstarted-boxes"
description: |-
  Instead of building a virtual machine from scratch, which would be a
  slow and tedious process, Vagrant uses a base image to quickly clone
  a virtual machine. These base images are known as "boxes" in Vagrant,
  and specifying the box to use for your Vagrant environment is always
  the first step after creating a new Vagrantfile.
---

# 盒子

Vagrant使用基本映像快速克隆虚拟机，而不是从零开始构建虚拟机，这将是一个缓慢而乏味的过程。
这些基本镜像在Vagrant中被称为"盒子"，指定一个盒子在你的Vagrant环境中使用总是创建一个新的Vagrantfile之后的第一步操作。

## 安装盒子

如果你在[入门概述页面](/intro/getting-started/)运行了命令行,那么你已经安装了一个盒子，你不需要再运行下面的命令。但是，阅读这一章节以了解更多关于盒子是如何管理的是非常值得的。

通过`vagrant box add`，盒子被添加到Vagrant。这将存储盒子在一个特别的名字下，以便多个Vagrant环境可以重用它。如果你还没有添加一个盒子，你现在可以这样做：

```
$ vagrant box add hashicorp/precise64
```

这将从[HashiCorp's Vagrant Cloud box catalog](https://vagrantcloud.com/boxes/search)下载一个名为"hashicorp/precise64"的盒子，你可以在这个网站查找或托管盒子。
虽然从HashiCorp's Vagrant Cloud下载盒子是非常容易的，你也可以从本地文件，自定义URL等地方添加盒子。

盒子被存储为对当前用户全局访问。每一个项目使用一个从原始镜像克隆来的盒子，而不会修改实际的原始镜像。这意味着如果你在两个项目中都使用了我们刚刚添加的`hashicorp/precise64`盒子，添加文件到一个客户端将不会影响到另一个客户端。

在上面的命令行中，你讲注意到盒子已经做了命名空间。盒子被分成两部分-用户名和盒子名-通过一个斜线分割。在上面的例子中，用户名是"hashicorp"，盒子名是"precise64"。你也可以通过URL或本地文件路径指定盒子，但在入门指南中不会包含此操作。

~> **命名空间不能保证盒子的权威！** 一个常见的误解是像"ubuntu"代表了Ubuntu盒子的权威空间。这是不恰当的。在Vagrant云中的命名空间起的作用和GitHub中的命名空间非常相似，例如，正如GitHub的支持团队无法协助某人的代码库中的问题，
HashiCorp的支持团队也无法协助第三方发布的盒子。

## 使用盒子
到目前为止，盒子已经被添加到了Vagrant，我们需要配置我们的项目，把盒子用作基础。打开 `Vagrantfile` 并修改下面的内容：

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
end
```

在这个例子中"hashicorp/precise64"必须和你在上面添加的box的名字相匹配。这就是Vagrant如何知道要使用哪个盒子。如果盒子之前没有添加过，Vagrant将会在运行时自动下载并添加盒子。

你可以通过设置 `config.vm.box_version` 指定盒子一个明确的版本号
例如：

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.box_version = "1.1.0"
end
```

你可以使用 `config.vm.box_url` 来指定一个URL到一个盒子的路径：

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
end
```

在下一节，我们将启动Vagrant环境并和它进行一些交互。

## 查找更多盒子


在这个入门指南的剩余部分，我们都只会使用我们之前已经添加的 "hashicorp/precise64" 盒子。但是在很快完成此入门指南后，你可能会提出的第一个问题是"我应该去哪里找到更多的盒子？"

查找更多盒子最好的一个地方就是[HashiCorp's Vagrant Cloud box catalog](https://vagrantcloud.com/boxes/search)。
HashiCorp's Vagrant Cloud拥有运行各种平台和技术的免费盒子公共目录。HashiCorp's Vagrant Cloud还有强大的搜索功能可以让你找到你关注的盒子相关的内容。

除了查找免费的盒子之外，HashiCorp's Vagrant Cloud还可以让你托管你自己的盒子，如果你打算为你的组织创建私有的盒子也是可以的。

## 下一步

你已成功下载了第一个Vagrant盒子并配置了Vagrantfile来利用此盒子。继续阅读以了解更多关于[启动Vagrant并通过SSH访问](/intro/getting-started/up.html)。
