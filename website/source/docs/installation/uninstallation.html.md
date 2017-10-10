---
layout: "docs"
page_title: "卸载Vagrant"
sidebar_current: "installation-uninstallation"
description: |-
  Uninstalling Vagrant is easy and straightforward. You can either uninstall
  the Vagrant binary, the user data, or both. The sections below cover how to
  do this on every platform.
---

# 卸载Vagrant

卸载Vagrant是简单直观的。你可以卸载Vagrant执行程序，用户数据，或者全部。下面的内容将涵盖如何在各平台上做这件事。

## 移除Vagrant程序

移除Vagrant程序将从你的机器上移除`vagrant`执行程序和所有依赖关系。在卸载执行程序后，你可以使用标准方法[重新安装](/docs/installation/)。

在 **Windows**

> 在控制面板使用添加/移除应用程序来进行卸载

在 **Mac OS X**:

```sh
rm -rf /opt/vagrant
rm -f /usr/local/bin/vagrant
sudo pkgutil --forget com.vagrant.vagrant
```

在 **Linux**:

```sh
rm -rf /opt/vagrant
rm -f /usr/bin/vagrant
```

## 移除用户数据

移除用户数据将会移除所有的[盒子](/docs/boxes.html),[插件](/docs/plugins/),许可文件，和其他Vagrant可能用到的任何文件。
移除用户数据有效的使Vagrant认为它将会是一个全新的安装。

在所有平台上，移除`~/.vagrant.d`目录就可以删除用户数据。在调试时，Vagrant的支持团队可能会问你是否要移除此目录。
在移除此目录前，请做好备份。

运行Vagrant将会自动的重新生成数据，因此在任何时间移除用户数据都是安全的。
