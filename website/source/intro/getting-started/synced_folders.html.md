---
layout: "intro"
page_title: "同步文件夹 - 开始使用"
sidebar_current: "gettingstarted-syncedfolders"
description: |-
  While it is cool to have a virtual machine so easily, not many people
  want to edit files using just plain terminal-based editors over SSH.
  Luckily with Vagrant you do not have to. By using synced folders, Vagrant
  will automatically sync your files to and from the guest machine.
---

# 同步文件夹

虽然轻松地拥有虚拟机很酷，但并不是很多人都想用简单的基于终端的编辑器来编辑文件。
幸运的是通过Vagrant你不必要那样做。通过_同步文件夹_，Vagrant将自动双向同步你的文件到虚拟机。

默认情况下，Vagrant将您的项目目录（请记住，这是Vagrantfile的目录）与guest虚拟机中的`/vagrant`目录共享。

如果你现在`vagrant ssh`进入你的虚拟机，那么你就会在`/home/vagrant`目录下。`/home/vagrant`是和已经进行同步的`/vagrant` 所不同的目录。

如果您的终端显示有关不兼容的访客添加（或没有添加访客）的错误，你可能需要更新你的盒子或者选择一个不同的盒子，如`hashicorp/precise64`。
有些用户通过使用vagrant-vbguest插件方成功的进行了访问，但这并没有被Vagrant核心团队官方支持。

再次运行`vagrant up`并SSH进入虚拟机：

```
$ vagrant up
...
$ vagrant ssh
...
vagrant@precise64:~$ ls /vagrant
Vagrantfile
```
不管你相信与否，你在虚拟机里看到的Vagrantfile实际上和你宿主机中的Vagrantfile是相同的。继续操作并创建一个文件向你证明这点：

```
vagrant@precise64:~$ touch /vagrant/foo
vagrant@precise64:~$ exit
$ ls
foo Vagrantfile
```

哇！"foo"现在已经在你的宿主机上面了。如同你看到的，Vagrant保持文件夹同步。

使用[同步文件夹](/docs/synced-folders/)，你可以继续在你的电脑上使用你喜爱的编辑器，文件会自动同步到虚拟机里。

## 下一步

已经成功地通过同步文件夹在客户机和你的宿主机进行了交互。继续阅读了解更多关于安装包，用户和更多[配置](/intro/getting-started/provisioning.html)。
