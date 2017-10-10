---
layout: "docs"
page_title: "从Vagrant 1.0升级"
sidebar_current: "installation-1-0-upgrading"
description: |-
  The upgrade process from 1.0.x to 1.x is straightforward. Vagrant is
  backwards compatible with Vagrant 1.0.x, so you can simply reinstall Vagrant
  over your previous installation by downloading the latest package and
  installing it using standard procedures for your operating system.
---

# 从Vagrant 1.0.x升级

从1.0.x到1.x的升级过程是非常简单的。Vagrant完全[向后兼容](/docs/installation/backwards-compatibility.html)Vagrant1.0.x，
因此你可以简单的通过你之前下载的最新版本的包进行重装Vagrant，用你操作系统的标准安装方式进行安装就可以了。

如同[向后兼容](/docs/installation/backwards-compatibility.html)页面所述，**Vagrant1.0.x插件将不会再Vagrant1.1以上版本工作**。
许多这些插件已经更新，可以使用较新版本的Vagrant，因此您可以查看这些插件是否已更新。 如果不是，您将不得不在升级之前删除它们。

建议您在升级之前删除_所有_插件，然后逐个添加回这些插件。 这样做通常会使升级过程更顺畅。

<div class="alert alert-warning" role="alert">
  <strong>如果您的Vagrant版本是通过Rubygems安装的</strong>，则必须先卸载旧版本，然后才能安装新版Vagrant的软件包。 不再支持Rubygems安装。
</div>
