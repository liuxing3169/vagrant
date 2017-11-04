---
layout: "docs"
page_title: "关于 Vagrant盒子"
sidebar_current: "vagrant-cloud-boxes"
---

# 关于Vagrant盒子
盒子是[Vagrant](https://vagrantup.com)环境下的包装格式。一个盒子可以被用在Vagrant支持的任意平台上，
从而带给开发团队一个统一的工作环境。

## Vagrant盒子创建和版本化

盒子支持版本化，因此团队的成员使用Vagrant可以轻松的更新基础盒子，创建盒子的人可以推送修复，而且这些修复会有效的进行传达。

Vagrant云可以轻松管理盒子的版本化。Vagrant云中的版本控制的盒子允许轻松更新，透明修复，并在所做的更改中清楚沟通。
了解更多关于[盒子发布生命周期](/docs/vagrant-cloud/boxes/lifecycle.html)。

## Vagrant盒子目录和发现

Vagrant云维护了一个公有可用的Vagrant盒子的目录。这些盒子是由HashiCorp和公共贡献者共同创建的。
你可以通过URL中他们的用户名或者盒子的介绍页面看到盒子的拥有者。

公有Vagrant盒子可以使你在一个不熟悉的环境下快速的启动并运行。
这是在一个组织或团体建立一个基本的开发环境，一个命令可启动的一种流行方式。