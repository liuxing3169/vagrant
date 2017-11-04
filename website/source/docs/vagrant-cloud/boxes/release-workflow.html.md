---
layout: "docs"
page_title: "API 发布流程"
sidebar_current: "vagrant-cloud-boxes-release-workflow"
---

# API 发布流程

通过Vagrant云网站来创建一个新盒子穿过它们的[发布生命周期](/docs/vagrant-cloud/boxes/lifecycle.html)是可行的，
但你也可以通过Vagrant云的API自动完成这些任务。

1. 创建盒子，或者定位盒子的`标签`，如 `hashicorp/precise64`
2. 在一些事情后，如在一个CI build结束后，你可能想要发布盒子的一个新版本。要做这件事，首先使用API创建一个带有版本号和变更简单解释说明的新版本
3. 然后，创建一些提供程序和版本进行关联，如 `virtualbox`
4. 一旦您的系统对API进行了必要的请求，并且该版本已经准备就绪，请向该版本的“release”端点发出请求
5. 该版本现在对用户可用了，可以通过命令“vagrant box outdated”或通过在`vagrant up` 自动对盒子检查新版本
