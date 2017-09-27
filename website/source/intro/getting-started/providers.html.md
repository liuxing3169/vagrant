---
layout: "intro"
page_title: "提供者 - 开始使用"
sidebar_current: "gettingstarted-providers"
description: |-
  In this getting started guide, your project was always backed with VirtualBox.
  But Vagrant can work with a wide variety of backend providers, such as VMware,
  AWS, and more. Read the page of each provider for more information on how to
  set them up.
---

# 提供者

在这个开始使用向导中，你的项目总是受[VirtualBox](https://www.virtualbox.org)支持。但是Vagrant可以和很多后台提供者进行一起工作，如[VMware](/docs/vmware/)，[AWS](https://github.com/mitchellh/vagrant-aws)和其他的一些等等。
阅读每一个提供者的页面了解更多信息关于如何建立起它们。

一旦你有了一个提供者已经安装好，你不需要对你的Vagrantfile做任何修改，只是运行`vagrant up`并带上provider参数，Vagrant将会完成剩下的工作：

```
$ vagrant up --provider=vmware_fusion
```

准备移动到云上？把它带到AWS：

```
$ vagrant up --provider=aws
```

一旦你运行`vagrant up`和其他的provider，不需要在告诉其他Vagrant命令要使用什么provider。
Vagrant可以自动找到它。因此，当你要SSH或destroy或其他的任何事情，仅正常运行命令就可以了，如 `vagrant destroy`。没有必要带上其它的标记。

关于更多与providers相关的信息，阅读[providers](/docs/providers/)的完整文档。

## 下一步

就这些了！你已经成功完成了Vagrant的开始使用向导。
这里有一些有趣的主题你可能会关注：
That's it! You have successfully completed the getting started guide for Vagrant.
Here are some interesting topics you might find relevant:

- [配置VirtualBox设置](/docs/virtualbox/)
- [使用插件](/docs/plugins/)
- [自定义同步文件夹](/docs/synced-folders/)
- [Provisioning with Puppet, Chef, or Ansible](/docs/provisioning/)
