---
layout: "docs"
page_title: "Vagrant云迁移"
sidebar_current: "vagrant-cloud-migration"
---

# Vagrant云迁移

与Vagrant相关的功能将从Terraform Enterprise转移到自己的产品Vagrant Cloud中。 此迁移目前计划于**2017年6月27日**美国东部时间下午6点（太平洋标准时间）/ 3PM  太平洋时间（UTC）/ 10PM。

届时所有现有的Vagrant盒子将被移动到新的系统。
所有的用户，组织和团队也将会被复制过去。

~> 如果你只使用Vagrant下载和运行公有盒子，那么没有什么改变。
~> 所有盒子名称，版本和URL将保持不变（或重定向），也不会更改您的工作流程或Vagrantfiles。

## Vagrant 盒子, 用户, 组织, 和团队

所有的Vagrant盒子都将会在6月27日被移到新的Vagrant云上。此外，所有的用户和组织都将被复制过去。
任何存在的盒子贡献者或团队访问控制规则都将会留存在新系统中。

所有现有的盒子名称（hashicorp/precise64）和URL将继续按原样工作，或永久重定向到正确的位置。 如果您只使用公有Vagrant盒子，则无需对Vagrantfiles或工作流进行更改。
私有Vagrant盒子的用户需要创建新的身份验证（请参阅下文），并在迁移完成后激活其Vagrant Cloud帐户。

如果在迁移后没有登录到Vagrant Cloud，Vagrant云用户和组织将在未来被视为不活跃，并且没有任何已发布的Vagrant盒子。
非活动用户帐户将于2017年10月1日或之后被删除。

## Vagrant云账号激活

为了开始使用你的Vagrant Cloud Atlas账号，你需要先激活你的Vagrant云账号。这个步骤会要求你登录到Atlas，以及确认您的密码（和2FA凭据，如果有配置）。 在Vagrant Cloud登录屏幕上将会有链接和说明，指导您这样做。

在Vagrant云账号激活期间，你将需要创建一个Vagrant云的新密码，并可选择配置2FA。
你之前存在的Atlas账号，密码和2FA配置将在Atlas中保留不变。

~> 新的Vagrant云用户可以总是可以随时免费创建一个新账号。

## 身份认证票据(Tokens)

如果您当前正在使用身份验证令牌与Atlas for Vagrant功能进行交互，则需要在6月27日之前生成新的Vagrant Cloud令牌。 您可以看到您的现有令牌，并在帐户设置的令牌页面上生成新的令牌。

创建此新令牌时，请选择迁移到Vagrant云。

你可以看到是哪个身份认证票据会被复制到Vagrant云的token列表中。

只有那些认证的Token会在6月27日被移动到Vagrant云中。
届时它们会被从Terraform Enterprise中移除，并将不再为Terraform或Packer操作工作。
如果您在6月27日之前未在Atlas中创建令牌，则需要在迁移后在Vagrant Cloud中创建令牌。

~> 通过`vagrant login`在Atlas中创建一个令牌也会将一个令牌标记为“迁移到Vagrant云”。

## Packer 和 Terraform Enterprise

Packer有两个post-processors，可以在Terraform Enterprise（Atlas）中创建Vagrant盒子：`atlas`和`vagrant-cloud`。
6月27日后，“atlas post-processor”将不再创建Vagrant盒子。
如果您目前正在使用Packer发布Vagrant盒子，请确保您使用的是Vagrant云post-processors。

例如, 是否你的Packer post-processor JSON 看起来像下面那样:

```json
{
  "variables": {
    "atlas_token": "{{env `ATLAS_TOKEN`}}",
    "version": "1.0.{{timestamp}}"
  },
  "builders": [
  ],
  "post-processors": [
    {
      "type": "atlas",
      "token": "{{user `atlas_token`}}",
      "artifact": "hashicorp/example",
      "artifact_type": "vagrant.box",
      "metadata": {
        "version": "{{user `version`}}"
      }
    }
  ]
}
```

You must replace the `atlas` post-processor with the `vagrant` and `vagrant-cloud` post-processors (note the nested array, which tells Packer to run these steps serially).

```json
{
  "variables": {
    "vagrantcloud_token": "{{env `VAGRANTCLOUD_TOKEN`}}",
    "version": "1.0.{{timestamp}}"
  },
  "builders": [
  ],
  "post-processors": [
    [
      {
        "type": "vagrant",
        "output": "output.box"
      },
      {
        "type": "vagrant-cloud",
        "access_token": "{{user `vagrantcloud_token`}}",
        "box_tag": "hashicorp/example",
        "version": "{{user `version`}}"
      }
    ]
  ]
}
```

## Vagrant分享

Vagrant Share via Atlas has been deprecated, and instead Vagrant supports native integration with [ngrok](https://ngrok.com).
Users of Vagrant Share should switch to the [ngrok-powered Vagrant Share driver](https://www.vagrantup.com/docs/share) prior to June 27th, which will become the default in the next version of Vagrant

## 停机时间

There will be a brief outage of Vagrant services within Atlas/Terraform Enterprise on June 27th at 6PM EDT/3PM PDT until the migration is complete.
We estimate that this will take less than 30 minutes.
