---
layout: "docs"
page_title: "盒子版本化和生命周期"
sidebar_current: "vagrant-cloud-boxes-lifecycle"
---

# 盒子版本化和生命周期

盒子支持版本化，因此团队的成员使用Vagrant可以轻松地更新底层盒子，而且创建盒子的人可以推送修复并让这些修复有效的进行传达。

这里有盒子的多个组件：

- 盒子本身，包含盒子的名称和描述。
- 一个或更多的盒子版本。
- 盒子的每一个版本的一个或更多程序提供者。

## Vagrant消息

执行`vagrant up`或 `vagrant box outdated`时，使用过时的盒子的用户将会在Vagrant中看到下面的消息：

    Bringing machine 'default' up with 'virtualbox' provider...
    ==> default: Checking if box 'hashicorp/example' is up to date...
    ==> default: A newer version of the box 'hashicorp/example' is available! You currently
    ==> default: have version '0.0.5'. The latest is version '0.0.6'. Run
    ==> default: `vagrant box update` to update.
    ...

## 盒子版本发布状态

Vagrant云可以让你创建盒子的一个新版本而不发布它们或者不在Vagrant看到更新。这就可以让你可以先准备好一个盒子，而后在慢慢发布。盒子版本有3种状态：

- `未发布`: Vagrant还不能看到这个版本，因此需要发布这个版本。可以通过编辑它们并点击页面上方的发布按钮来发布这个版本。
- `有效的`: Vagrant可以添加和使用这个版本
- `已回收的`: Vagrant不能看到这个版本，而且它不能被重新发布。你必须再重新创建一个版本

### 发布前提

一个盒子的每个组件(一个盒子，一个版本和一个提供程序)至少有一个才可以被发布。
