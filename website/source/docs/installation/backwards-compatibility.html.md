---
layout: "docs"
page_title: "向后兼容性"
sidebar_current: "installation-backwards-compatibility"
description: |-
  Vagrant makes a very strict backwards-compatability promise.
---

# 向后兼容性

## 对于1.0.x

Vagrant 1.1以上版本提供了完整向后兼容有效的Vagrant 1.0.x Vagrantfiles且不需任何插件。
安装Vagrant1.1之后，你的1.0.x环境应该可以继续工作而不需要做任何修改，已经运行的机器可以继续正确的被管理。

这种兼容层将会保留在Varant中，包含Vagrant2.0。在此之后可能还会继续存在。但是Vagrant的兼容性许诺是只对2个版本。
鉴于Vagrant的主干发行会花费数年来开发和发布，因此你的1.0.x版本的Vagrantfile会暂时安全。

如果你使用了任何1.0.x的插件，你必须从你更新之前从Vagrantfile移除这些引用。
Vagrant1.1以上版本包含了新的插件，这种格式将防止这种与之不相容的形式再次发生。

## 对于1.x
1.x之间的向后兼容性不被承诺，Vagrantfile的语法稳定性在2.0 final之前是不被承诺的。 1.x中的任何向后不兼容性将被清楚地记录在案。

这与Vagrant 0.x的处理方式类似。 在实践中，Vagrant 0.x在整个开发周期中仅引入了一些向后的不兼容性，但是向后不兼容的可能性是明确的，所以人们并不感到惊讶。

Vagrant 2.0最终将具有稳定的Vagrantfile格式，将保持向后兼容，就像1.0被认为是稳定的。