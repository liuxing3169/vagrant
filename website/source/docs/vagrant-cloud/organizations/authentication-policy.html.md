---
layout: "docs"
page_title: "组织身份认证策略"
sidebar_current: "vagrant-cloud-organizations-authentication-policy"
---


# 设置一个组织身份认证策略

由于组织成员资格允许成员访问潜在的敏感资源，拥有者可以在Vagrant Enterprise中设置组织范围内的身份验证策略。

## 要求双重身份认证

组织拥有者可以要求所有的组织团队成员都使用[双重身份认证](/docs/vagrant-cloud/users/authentication.html).
那些缺乏双因素身份验证的人将被锁定在web界面之外，直到他们启用双重身份认证或离开组织。

浏览你的组织配置页面，启用这个功能。所有组织拥有者必须进行双重认证才能请求组织内的实施。
注意：锁定的用户还可以继续使用他们的`ATLAS_TOKEN`和Vagrant云进行交互。

## 禁用双重身份认证请求

组织拥有者可以从他们的组织配置页面禁用双重身份认证要求。锁定的团队成员(那些不能进行双重身份认证的人)将会恢复他们的会员权益。
