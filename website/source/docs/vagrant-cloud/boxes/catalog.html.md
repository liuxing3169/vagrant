---
layout: "docs"
page_title: "发现Vagrant盒子"
sidebar_current: "vagrant-cloud-boxes-catalog"
---

# 发现Vagrant盒子

Vagrant云提供一个公有，可搜索的Vagrant盒子的索引。通过使用Vagrant你可以轻松找到一个盒子，它包含了一个Vagrant环境所需的技术。

使用公有盒子时，你不需要一个Vagrant云账号。

1. 去到[盒子搜索页面](https://vagrantcloud.com/boxes/search)

1. 一旦你找到一个盒子，点击它的名字了解它的更多信息。

1. 当你准备使用时，复制它的名字，如"hashicorp/precise64"并用`vagrant init hashicorp/precise64`初始化你的Vagrant项目。
或者，如果你已经创建了一个Vagrant项目，修改Vagrantfile以使用这个盒子：`config.vm.box = "hashicorp/precise64"`

## 提供者支持

不是所有的盒子对所有的提供者可见。你可能需要由本地系统上的提供者进行排序以缩小搜索范围。

## 选择正确的盒子

与从公共来源使用的所有软件和配置一样，重要的是要记住您使用的是谁的盒子。当你选择一个盒子时，有一些时间需要注意：

- __用户的用户名__。 如果是`bento` 或者 `canonical`, 你可以信任这种盒子超过匿名用户
- __盒子的下载量__。 大量被下载过的盒子可能类似于更多其他的社区成员已经审查过。Hashicorp回应了通过Vagrant Cloud分发的恶意软件的报告，并取消了盒子
- __最后的发布日期__。 更多一些的更新的盒子包含了更新一些的软件
- __盒子是否可下载__。 Vagrant Cloud会定期检查盒子是否可公开访问。你可以在盒子的页面上的提供者处看到此信息