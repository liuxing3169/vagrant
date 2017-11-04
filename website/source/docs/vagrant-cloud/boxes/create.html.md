---
layout: "docs"
page_title: "创建一个新的Vagrant盒子"
sidebar_current: "vagrant-cloud-boxes-create-x"
---

# 创建一个新的Vagrant盒子

这个页面涵盖了在Vagrant云中创建一个新盒子和如何将它分发给用户。盒子可以不通过Vagrant云进行分发，但是会错过一些[重要的特性](/docs/vagrant-cloud/boxes)。

这里有_三种方式来创建和上传Vagrant盒子到Vagrant云_。三种选项都列在下面。

我们建议使用Packer，因为它是完全可重复的，并保持在Vagrant Cloud中有很强大的变化历史。
无论如何，在一些情景下，包括一些遗留的工作，Web UI或API等。

所有这三种方式都要求你[注册Vagrant云账号](https://vagrantcloud.com/account/new)。

## 使用Packer创建盒子

使用Packer需要更多的前期工作，但可重复和自动化的构建将结束对盒子的任何手动管理。此外，所有的盒子都将被在Vagrant云上进行存储和提供，保持变更历史。

## 通过Vagrant云Web接口创建盒子

你需要先创建一个盒子文件。这可以通过[vagrant `package` command](http://docs.vagrantup.com/v2/boxes/base.html)完成或通过本地Packer。

在你创建完`.box`文件后，可以遵循这个向导。

1. 去到创建[盒子](https://vagrantcloud.com/boxes/new)页面。

1. 命名盒子并给它一个简单的解释说明

1. 创建你盒子的首个版本。这个版本必须匹配格式 `[0-9].[0-9].[0-9]`

1. 为盒子创建一个提供者，匹配你需要在本地的Vagrant中使用的提供者。`virtualbox`是一个非常常用的提供者。

1. 为每一个提供者上传 `.box`文件，或者使用一个可以公共访问的 `.box`文件的url

你可以在Vagrant Cloud中[Vagrant section](https://vagrantcloud.com/vagrant)找到你所有的盒子。

当你创建并发布了一个盒子，你可以通过点击盒子页面"创建新版本"来发布盒子新的版本。关于更多盒子的发布生命周期的更多信息，请参考[专用于盒子生命周期的帮助页面](/docs/vagrant-cloud/boxes/lifecycle.html)。

## 使用API创建盒子

这个例子使用API通过`curl`上传盒子。开始使用，你需要获取一个[访问票据(access token)](https://vagrantcloud.com/settings/tokens)。

然后，准备上传：

    $ curl 'https://vagrantcloud.com/api/v1/box/USERNAME/BOX_NAME/version/VERSION/provider/PROVIDER_NAME/upload?access_token=ACCESS_TOKEN'

这将会返回类似下面的信息：

    {
      "upload_path": "https://archivist.hashicorp.com/v1/object/630e42d9-2364-2412-4121-18266770468e"
    }
然后，使用下面的命令上传你的盒子，在这个例子中文件名会是`foo.box`：

    $ curl -X PUT --upload-file foo.box https://archivist.hashicorp.com/v1/object/630e42d9-2364-2412-4121-18266770468e

当上传完成后，您可以通过发出这个请求并匹配“hosted_token”返回到先前检索到的上传令牌来进行验证。

    $ curl 'https://vagrantcloud.com/api/v1/box/USERNAME/BOX_NAME/version/VERSION_NUMBER/provider/PROVIDER_NAME?access_token=ACCESS_TOKEN'

你的盒子应该已经可以下载了。
