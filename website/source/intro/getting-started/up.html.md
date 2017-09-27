---
layout: "intro"
page_title: "启动和SSh - 开始使用"
sidebar_current: "gettingstarted-up"
description: |-
  It is time to boot your first Vagrant environment. Run the following from your
  terminal - "vagrant up"
---

# 启动和SSH

是时候启动你的第一个Vagrant环境了。在你的终端中运行下面的命令：
It is time to boot your first Vagrant environment. Run the following from your
terminal:

```
$ vagrant up
```

在不到一分钟内，这个命令将执行完成，然后你讲拥有一个运行着Ubuntu的虚拟机。你将不会_看到_任何东西，因为Vagrant运行虚拟机时不带UI。为了检验它确实是在运行中，你可以通过SSH进入虚拟机：

```
$ vagrant ssh
```

这个命令将带你进入一个完全的SSH回话中。继续操作机器做你想做的任何事。尽管它可能被暂存，还是要小心 `rm -rf /`，因为Vagrant共享`/vagrant`目录和你Vagrantfile中包含的宿主机的目录，而且可以删除所有这些文件。
共享文件夹将会在下一节进行讨论。

思考一下刚刚发生了什么：通过仅一行配置和终端中的一条命令，我们建立了一个全功能的，SSH可访问的虚拟机。Cool, SSH会话可以用 `CTRL+D` 终止。

```
vagrant@precise64:~$ logout
Connection to 127.0.0.1 closed.
```

当你摆弄完机器后，回到你的宿主机上运行`vagrant destroy`，Vagrant将会终结通过虚拟机用到的任何资源。

-> `vagrant destroy` 命令不会真正的移除下载的box文件。要_ 彻底地_移除box文件，你可以使用 `vagrant box remove` 命令。

## 下一步

你已经成功地创建并和你的第一个Vagrant环境进行了交互！继续阅读以了解更多关于[同步文件夹](/intro/getting-started/synced_folders.html)。