---
layout: "docs"
page_title: "从源文件安装Vagrant"
sidebar_current: "installation-source"
description: |-
  Installing Vagrant from source is an advanced topic and is only recommended
  when using the official installer is not an option. This page details the
  steps and prerequisites for installing Vagrant from source.
---

# 从源文件安装Vagrant

从源文件安装Vagrant是一个高级话题，仅建议在使用官方安装器不是一个选项时使用。
这个页面介绍了从源文件安装Vagrant的详细步骤和前提条件。

## 安装Ruby
你必须有一个现代的Ruby (>= 2.2)以便开发和编译Vagrant。Vagrant的`gemspec`中记录了具体的Ruby版本。
请参考GitHub代码仓库中的`vagrant.gemspec`，它会包含更多的最新的需求。
这个向导将不会解释如何安装和管理Ruby。无论如何，小心一下陷阱：

- 请 **不要** 使用系统自带的Ruby - 使用一个Ruby版本管理器，例如rvm或chruby
- 基于当前环境配置Vagrant插件。如果使用Vagrant从源文件中安装插件，则它们无法从基于包的Vagrant安装中正常工作。

## 克隆Vagrant
从GitHub克隆Vagrant的代码仓库到你电脑上保持编码的路径：

```shell
$ git clone https://github.com/mitchellh/vagrant.git
```

下一步, `cd` 到这个路径。所有的命令都将从这个路径开始运行：

```shell
$ cd /path/to/your/vagrant/clone
```

运行`bundle` 命令，带上一个必需的版本*以安装前置条件：

```shell
$ bundle install
```

你现在可以从刚才的路径下通过运行`bundle exec vagrant` 运行Varant。

## 使用本地
为了在其他的项目中使用你本地安装版本的Vagrant，你将需要创建一个binstub并将它添加到你的path变量中。

首先，从Vagrant仓库运行下面的命令：
```shell
$ bundle --binstubs exec
```

这将会在`exec/`生成文件，包含`vagrant`。现在可以在你的操作系统任何地方指定到`exec/vagrant`的全路径：

```shell
$ /path/to/vagrant/exec/vagrant init -m hashicorp/precise64
```

注意你将收到警告，如运行Vagrant不被允许。这些警告是真的。你应该听取这些警告的建议。

如果你不想指定到Vagrant的全路径(例如，你只是想运行`vagrant`),你可以创建一个到你执行路径的软连接：

```shell
$ ln -sf /path/to/vagrant/exec/vagrant /usr/local/bin/vagrant
```

当你想切换回官方Vagrant版本，简单的移除软连接就可以了。

