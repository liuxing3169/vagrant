---
layout: "intro"
page_title: "拆卸 - 开始使用"
sidebar_current: "gettingstarted-teardown"
description: |-
  We now have a fully functional virtual machine we can use for basic
  web development. But now let us say it is time to switch gears, maybe work
  on another project, maybe go out to lunch, or maybe just time to go home.
  How do we clean up our development environment?
---

# 拆卸

我们现在有一个完整功能的虚拟机，我们可以用它作基础的Web开发。
但现在让我们说现在是切换齿轮的时候了，也许在另一个项目上工作，也许出去吃午饭，或者也许只是时间回家了。
我们如何清理我们的开发环境?

使用Vagrant，你可以_挂起_，_停止_ 或_销毁_ 虚拟机。这些选项中的每一个都有优点和缺点。选择最适合你的方式。

**挂起** 通过调用 `vagrant suspend` 虚拟机将保存当前的运行状态并停止机器。当你准备再一个开始工作时，只需要运行 `vagrant up`，
它将恢复到你离开的地方。这个方法的主要好处是它非常的快，通常只需要花费5到10秒就可以停止和启动你的工作。负面的地方是虚拟机将会继续占用着你的磁盘空间，
需要磁盘中的更多的地方来存储虚拟机的RAM的所有状态。

**停止** 通过调用`vagrant halt`将正常地关闭客户机操作系统并关闭虚拟机。
当你准备再一次启动它时，你可以使用`vagrant up`。这个方法的好处是它将干净利索地关闭你的虚拟机，保存磁盘的内容，并允许它再一次干净利索的启动。
负面的地方是它将花费一小会时间冷启动，虚拟机仍会占用磁盘空间。

**销毁** 通过调用`vagrant destroy`将从你的系统中移除虚拟机所有的痕迹。它将停止客户机，断开它的电源，移除虚拟机的所有虚拟硬盘。
再次，当你准备开始工作是，仅需输入`vagrant up`。这样做的好处是没有碎片留在你的机器上。虚拟机所占用的磁盘空间和内存空间都将被释放，你的宿主机变得干净。
负面的地方是再次开始工作时`vagrant up`将会花费一些时间，因为它将重新导入虚拟机并重新配置它。

## 下一步

你已经使用Vagrant成功地挂起，停止和销毁了你的虚拟环境。继续阅读了解更多关于如何[重建环境](/intro/getting-started/rebuild.html)。
