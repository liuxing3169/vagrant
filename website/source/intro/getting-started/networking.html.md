---
layout: "intro"
page_title: "网络 - 开始使用"
sidebar_current: "gettingstarted-networking"
description: |-
  At this point we have a web server up and running with the ability to
  modify files from our host and have them automatically synced to the guest.
  However, accessing the web pages simply from the terminal from inside
  the machine is not very satisfying. In this step, we will use Vagrant's
  networking features to give us additional options for accessing the
  machine from our host machine.
---

# 网络
此时，我们已经有了一个Web服务器已经启动并运行着，可以在宿主机中修改文件，然后它们可以自动和虚拟机进行同步。
但是，在虚拟机的终端中简单的访问web页面不是很让人满足。在这一步中，我们将会使用Vagrant的_网络_ 功能以使我们可以从本机访问虚拟机。

## 端口映射

一个选项是使用_端口映射_。端口映射允许你指定虚拟机的一个端口共享宿主的一个端口。
这就允许你通过你自己的电脑访问这个端口，但实际上会将所有网络流量通过这个接口转发到客户机上的一个特定端口。

让我们建立一个端口映射以便我们可以在我们自己电脑上访问Apache。此操作是非常简单的，编辑Vagrantfile，内容如下格式：

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.network :forwarded_port, guest: 80, host: 4567
end
```

运行`vagrant reload`或者`vagrant up`（依赖于这个机器是否正在运行中）使这些改变生效。


当机器重新运行时，在浏览器中浏览`http://127.0.0.1:4567` 。你可以看到一个从虚拟机中运行并通过Vagrant自动启动的web页面。

## 其他网络

Vagrant还有其他的网络形式，允许你分配一个静态IP地址给虚拟机，或许桥接虚拟机与现有已存在的网络。如果你对其他选项感兴趣，阅读[网络页](/docs/networking/)。

## 下一步

你已经通过Vagrant成功为你的虚拟机配置了网络。继续阅读以了解更多关于[通过Vagrant建立分享](/intro/getting-started/share.html)。
