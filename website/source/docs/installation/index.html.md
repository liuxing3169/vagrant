---
layout: "docs"
page_title: "安装Vagrant"
sidebar_current: "installation"
description: |-
  Installing Vagrant is extremely easy. Head over to the Vagrant downloads page
  and get the appropriate installer or package for your platform. Install the
  package using standard procedures for your operating system.
---

# 安装Vagrant

安装Vagrant是非常的简单。前往[Vagrant下载页](/downloads.html)获取对你的操作系统相适应的安装器或包。
用你操作系统的标准的程序安装方式安装此安装包。

安装程序会自动添加`vagrant` 到系统的环境变量中，这样就可以在终端中使用Vagrant命令。
如果没有找到命令，请试一下登出再重新登录操作系统(通常在Windows下比较需要这样做)。

<div class="alert alert-warning" role="alert">
  <strong>寻找gem安装?</strong> Vagrant 1.0.x 有选项可以被安装成为一个<a href="https://en.wikipedia.org/wiki/RubyGems">RubyGem</a>。这种安装方式不会被一直支持。如果你有一个通过Rubygems安装的旧版本的Vagrant，请移除它，然后安装新版本的Vagrant。
</div>

<div class="alert alert-warning" role="alert">
  <strong>当心系统包管理器！</strong> 一些操作系统分发包括一个vagrant包到它们的上游包仓库中。
  请不要通过这种管理器安装Vagrant。通常这种包会缺失依赖或包含非常过时的Vagrant。如果你是通过你的系统包管理器安装的，这很可能让你经历一些问题。请使用下载页面中的官方安装器进行安装。
</div>
