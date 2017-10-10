---
layout: "docs"
page_title: "升级Vagrant"
sidebar_current: "installation-upgrading"
description: |-
  If you are upgrading from Vagrant 1.0.x, please read the specific page
  dedicated to that. This page covers upgrading Vagrant in general during the
  1.x series.
---

# 升级Vagrant

如果你要从Vagrant1.0.x升级过来，请阅读[专门做此事的页面](/docs/installation/upgrading-from-1-0.html)。
这个页面涵盖了在1.x系列中升级Vagrant通常会遇到的问题。

在1.x的Vagrant间进行升级是非常简单的：

1. [下载](/downloads.html)最新安装包
2. 安装它，覆盖已经存在的包

安装器会正确的覆盖和移除旧文件。建议在升级过程中不要运行其他Vagrant进程。

请注意，新的Vagrantfile语法的Vagrantfile稳定性不会承诺，直到2.0 final。
因此为1.0.x所作的Vagrantfiles将会[继续可用](/docs/installation/backwards-compatibility.html),
新版本的Vagrantfiles可能会向后不兼容直到2.0final。

<div class="alert alert-info alert-block">
  <strong>在升级时运行时遇到麻烦？</strong> 请
  <a href="https://github.com/mitchellh/vagrant/issues" class="alert-link">报告一个问题</a>
  如果你在升级时运行到一个问题中。升级意味着将是一个顺滑的过程，否则我们会认为这是一个bug。
</div>
