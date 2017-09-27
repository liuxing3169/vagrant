---
layout: "intro"
page_title: "配置 - 开始使用"
sidebar_current: "gettingstarted-provisioning"
description: |-
  We have a virtual machine running a basic copy of Ubuntu and we can edit files
  from our machine and have them synced into the virtual machine. Let us now
  serve those files using a webserver.
---

# 配置

好吧，我们有了一个运行Ubuntu的一个虚拟机并且我们可以在你的电脑上编辑文件，然后它们就会同步到虚拟机里。
让我们用一个web服务器运行期这些文件。

我们可以SSH进到虚拟机并用我们自己的方式安装一个web服务器，但是之后每个使用Vagrant的人都需要做同样的事情。
Vagrant有内置的支持_自动配置_。使用这个功能，Vagrant将会在你执行`vagrant up`时自动安装软件，因此虚拟机可以被重复创建和随时可用。

## 安装Apache

我们将会为我们的基础项目建立起[Apache](http://httpd.apache.org/)，我们会使用sheell脚本做这件事。创建下面的shell脚本，并将它保存为`bootstrap.sh` ，放在和Vagrantfile相同的目录中：

```bash
#!/usr/bin/env bash

apt-get update
apt-get install -y apache2
if ! [ -L /var/www ]; then
  rm -rf /var/www
  ln -fs /vagrant /var/www
fi
```

下一步，我们配置Vagrant在运行我们的虚拟机时运行这个shell脚本。我们通过编辑Vagrantfile完成此事，如下所示：

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.provision :shell, path: "bootstrap.sh"
end
```

"provision" 行是新加的行，它告诉Vagrant启动虚拟机时使用`shell` 运行 `bootstrap.sh`。这个文件的路径是相当于本地项目根目录(Vagrantfile文件存放路径)的相对路径。

## 配置!

在各配置项都完成后，运行`vagrant up`以创建你的机器，Vagrant将会自动完成配置。你应该可以在你的终端中看到shell脚本的相关输出。如果在上一步，虚拟机已经在运行中，运行`vagrant reload --provision`命令，这操作会快速重启你的虚拟机，跳过初始导入步骤。
重新加载的命令中的配置标记会命令Vagrant运行配置项，因为通常Vagrant只会在第一次执行`vagrant up`时执行配置。

在Vagrant完成运行后，Web服务器将会自动的启动和运行。你在你的浏览器中还不能访问这个网站，但你可以通过从SSH加载一个文件来验证配置已生效：

```
$ vagrant ssh
...
vagrant@precise64:~$ wget -qO- 127.0.0.1
```

这已经生效因为在上面的shell脚本中，我们已经安装了Apache并设置Apache的默认`DocumentRoot` 到`/vagrant`目录，这是通过Vagrant建立的默认同步文件夹。

你可以通过创建更多文件做更多的事情，并在终端中看到，但是在下一节我们将涉及网络选项，让你可以用你的浏览器访问虚拟机中网站。

-> **对于那些复杂的配置脚本**, 打包一个自定义的已经预装了包的Vagrant盒子可能会更高效，这样就不用每次都创建这些。
这个主题没有包含在开始使用中，但可以在[打包一个自定义盒子](/docs/boxes/base.html)中找到相关文档。

## 下一步

你已经成功配置了你的第一个Vagrant的虚拟机。继续阅读以了解更多关于[网络](/intro/getting-started/networking.html)。
