---
layout: "docs"
page_title: "盒子版本化"
sidebar_current: "boxes-versioning"
description: |-
  Since Vagrant 1.5, boxes support versioning. This allows the people who
  make boxes to push updates to the box, and the people who use the box
  have a simple workflow for checking for updates, updating their boxes,
  and seeing what has changed.
---

# 盒子版本化

从Vagrant 1.5起，盒子支持版本化。这就允许创建盒子的人们可以推送更新给盒子，
而且使用盒子的人们可以用一个简单的工作流程检查更新，更新他们的盒子，并可以看到什么发生了改变。

如果你只是开始使用Vagrant，盒子版本化不是非常重要，我们建议你先学习一些其他主题。
但如果你是在团队中使用Vagrant或者计划创建你自己的盒子，版本化是非常重要的。
幸运的是，有了版本化建立正确的到Vagrant让使用变的更容易，Vagrant工作流更美好。

这个页面会涵盖如何使用版本化的盒子。不会涵盖如何通过版本更新你自己的盒子。那个主题在[创建一个基础盒子](/docs/boxes/base.html)。

## 查看版本和更新

`vagrant box list` 仅显示_已经安装的_盒子的版本。如果你想查看盒子所有可用的版本，你需要在[HashiCorp's Vagrant云](/docs/vagrant-cloud)上查找盒子。
查找盒子一种简单的方式时使用url `https://vagrantcloud.com/$USER/$BOX`。例如，对于`hashicorp/precise64`这个盒子，你可以在`https://vagrantcloud.com/hashicorp/precise64`找到它的相关信息。

你可以通过`vagrant box outdated`命令检查你正在使用的盒子是否已经过时。
这可以检查你当前的Vagrant环境中的盒子是否已经过时，也可以检查你操作系统中的其他已经安装的盒子。

最后，你可以通过`vagrant box update`命令来更新盒子。这将会下载并安装新的盒子。这将不会更新正在运行中的Vagrant环境。
如果Vagrant环境已经在运行中，你需要销毁并重新创建它以获取最新的更新到盒子里。更新命令仅下载这些更新到本地。

## 版本约束

你可以使用[Vagrantfile](/docs/vagrantfile/)文件中`config.vm.box_version`选项强制Vagrant环境使用一个指定的版本或指定版本的盒子。

如果这个选项没有被指定，总是会使用最新版本。这也等同于指定约束">= 0"。

盒子的版本配置可以是一个指定的版本或者是版本约束。约束可以使下列的任何形式：`= X`, `> X`, `< X`, `>= X`, `<= X`, `~> X`。
你可以通过逗号分割组合使用多种约束。所有的约束都可以用`~>`进行自解释除外可能，常被理解为“悲观约束”。
举例说明进行解释：`~> 1.0`等于`>= 1.0, < 2.0`。`~> 1.1.5`等于`>= 1.1.5, < 1.2.0`。

你可以选择处理你认为合适的版本。然而，公共目录中的很多盒子遵循[语义化的版本](http://semver.org/)。
基本上，只有第一个数字(“主版本”)打破了向后兼容性。在Vagrant盒子的条件中，这意味着任何在版本1.1.5"的盒子中的任何软件都可以在"1.2" and "1.4.5"等版本中正常工作。但是"2.0"可能包含一个较大的改变，会破坏你的软件。遵循这种惯例，最好的约束是`~> 1.0`，因为你知道它是安全的，无论是这个区间的任何版本。

请注意，semantic versioning规格允许多于三点和pre-release或beta版本，但是Vagrant盒子必须是`X.Y.Z`的格式，且`X`,`Y`,`Z`都是正整数。

## 自动更新检查

使用[Vagrantfile](/docs/vagrantfile/)，你还可以配置Vagrant在任意`vagrant up`时自动检测更新。默认情况下是开启的，
但你可以在Vagrantfile中设置`config.vm.box_check_update = false` 轻松禁用。

当这个自动更新是开启时，Vagrant将会自动检测更新在每一次`vagrant up`时，
不仅是机器从scratch创建时，还在它重启时，挂起后继续运行时等情况。

如果找到了一个更新，Vagrant会输出一个警告给用户，让用户知道有一个更新可用了。
然后用户可以选择暂时忽略这个警告，或者通过运行`vagrant box update`命令更新盒子。

Vagrant不能也不会自动的下载更新的盒子并更新虚拟机，因为盒子可能是非常大的，而且更新虚拟机需要销毁并重新创建它，这可能会导致重要的数据丢失。
因此，该过程是手动的，用户必须手动输入命令才能执行此操作。

## 删除旧版本

Vagrant不会自动地删除旧版本，因为它不知道这些旧版本是否被其他的Vagrant环境使用中。
因为盒子可以很大，所以你可能想要一次使用`vagrant box remove`来主动删除它们。
你可以用`vagrant box list`命令查看所有已经安装的盒子。

另外一个选项是使用`vagrant box prune`命令来移除所有已经安装的过时的盒子和当前没有使用的盒子。
