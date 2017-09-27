---
layout: "intro"
page_title: "Install Vagrant - Getting Started"
sidebar_current: "gettingstarted-install"
description: |-
  Installing Vagrant is extremely easy. Head over to the Vagrant downloads page
  and get the appropriate installer or package for your platform. Install the
  package using standard procedures for your operating system.
---

# 安装Vagrant

Vagrant必须在你想要运行它之前先安装在机器上。为了让安装更简单，Vagrant被分发成各种[安装包](/downloads.html)以支持所有的平台和系统。
这个页面将覆盖如何从源代码中编译Vagrant，这些内容包含在[README](https://github.com/mitchellh/vagrant/blob/master/README.md)中，仅建议高级用户使用。

## 安装Vagrant

要安装Vagrant，首先找到对你的系统适用的[适当的安装包](/downloads.html)并下载它。Vagrant是一种特定操作的包。
在你的操作系统上运行安装器。安装器会自动添加`vagrant`到你的系统目录，以使命令可以在终端命令中运行。如果没有找到，请尝试登出系统并重新进入系统（这可能在Windows下会需要）。

## 验证安装

安装完Vagrant后，通过打开一个新的命令窗口或控制台来验证安装完成，并检查`vagrant`可以使用：

```text
$ vagrant
Usage: vagrant [options] <command> [<args>]

    -v, --version                    Print the version and exit.
    -h, --help                       Print this help.

# ...
```

## 警告

~> **当心系统包管理器！** 一些操作系统分发包括其上游包裹中的流氓软件包。 请不要以这种方式安装Vagrant。 通常，这些软件包缺少依赖关系，或者包含非常过时的Vagrant版本。 如果您通过系统的软件包管理器安装，很有可能会遇到问题。 请使用下载页面上的官方安装程序。

## 下一步


您已成功下载并安装Vagrant！了解更多关于[创建你的第一个Vagrant项目](/intro/getting-started/project_setup.html)。
