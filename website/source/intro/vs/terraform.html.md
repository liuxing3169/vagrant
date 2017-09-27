---
layout: "intro"
page_title: "Vagrant vs. Terraform"
sidebar_current: "vs-terraform"
description: |-
  Vagrant is a tool for managing virtual machines. Terraform is another open
  source tool from HashiCorp which enables infrastructure as code.
---

# Vagrant vs. Terraform

Vagrant和[Terraform][terraform]都是[HashiCorp][hashicorp]的项目。Vagrant是一个专注于管理开发环境的工具，Terraform是构建基础设施的工具。

Terraform可以描述本地或远程存在的复杂的基础设施集。它专注于随着时间的推移建立和改变基础设施。 虚拟机生命周期的最小方面可以在Terraform中复制，有时会导致与Vagrant的混淆。

Vagrant提供了Terraform没有的一些更高级功能。 同步的文件夹，自动联网，HTTP隧道等等都是Vagrant为减轻开发环境使用而提供的功能。 由于Terraform专注于基础设施管理而不是开发环境，因此这些功能超出了该项目的范围。

Terraform的主要用途是用于管理云提供商（如AWS）中的远程资源。 Terraform旨在能够管理跨越多个云提供商的超大型基础架构。 Vagrant主要用于最多只使用少量虚拟机的本地开发环境。

Vagrant是用于开发环境。 Terraform用于更一般的基础设施管理。

[hashicorp]: https://www.hashicorp.com
[terraform]: https://www.terraform.io
