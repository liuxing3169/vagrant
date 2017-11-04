---
layout: "docs"
page_title: "分发盒子"
sidebar_current: "vagrant-cloud-boxes-distributing"
---

## 分发盒子

分发盒子给你的团队，更新你的Vagrantfile以引用Vagrant云上的盒子。

    Vagrant.configure(2) do |config|
      config.vm.box = "username/example-box"
    end

现在当团队的成员运行`vagrant up`时，盒子将会被从Vagrant云上下载。如果盒子是私有的，那么团队成员将会被提示进行身份认证。
通过账户名和密码登录到Vagrant云上或者通过使用一个共享的Vagrant云token，用户就会获取私有资源的访问权限。
[了解更多关于授权选项](/docs/vagrant-cloud/users/authentication.html).

## 私有盒子

如果你创建了一个私有盒子，只有你(拥有者)和贡献者可以访问它。如果你的盒子中有信息，数据或配置不能公开，这将是很有价值的。

私有盒子将会被从盒子目录中排除。

### 合作者

合作者可以是组织中的团队或者个人用户。

添加一个合作者：

1. 通过侧边栏到盒子的“访问”页面
2. 输入用户名或者团队名称并提交表单
3. 你将会看到用户或团队已经在贡献者列表中了，如果需要，你可以移除贡献者

### Vagrant登录

为了在Vagrant访问这些私有盒子，你需要先认证你的Vagrant云账号。

1. 运行 `vagrant login`
2. 输入你的凭证

你应该已经登录了。我们使用这些凭证来请求一个唯一身份认证票据(token)存储到本地。你的用户名或密码永远不会被保存到你的电脑上。

### 404 未找到

如果你没有完成身份认证，你讲会看到一个Vagrant`404 Not Found`错误。我们因安全原因返回404,因此一些潜在的破坏者就不能验证是否有一个私有盒子存在。
