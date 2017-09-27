---
layout: "intro"
page_title: "Vagrant vs. CLI Tools"
sidebar_current: "vs-cli-tools"
description: |-
  Virtualization software like VirtualBox and VMware come with command line
  utilities for managing the lifecycle of machines on their platform. Vagrant
  actually uses many of these utilities internally. The difference between these
  CLI tools and Vagrant is that Vagrant provides a declarative, reproducible,
  idempotent workflow.
---

# Vagrant vs. CLI Tools

VirtualBox和VMware等虚拟化软件配有命令行实用程序，用于管理其平台上的机器的生命周期。许多人利用这些实用程序编写自己的自动化。 Vagrant实际上在内部使用了许多这些工具。

这些CLI工具和Vagrant之间的区别在于，Vagrant用一些方法构建在这些实用程序之上，同时仍然提供一致的工作流程。Vagrant支持多个同步的文件夹类型，多个配置器设置机器，自动SSH设置，在您的开发环境中创建HTTP隧道等。 所有这些可以使用一个简单的配置文件进行配置。

即使您忽略Vagrant提供的所有高级功能，Vagrant仍然会对手动脚本进行一些改进。 虚拟化软件提供的命令行实用程序通常会在每个版本改变，或者具有解决方法的微妙错误。 Vagrant会自动检测版本，使用正确的标志，并且可以解决已知问题。 因此，如果您使用的是VirtualBox的一个版本，并且同事正在使用不同的版本，Vagrant仍将始终如一地工作。

对于不经常更改的高度特定的工作流程，维护自定义脚本仍然是有益的。 Vagrant旨在构建开发环境，但一些高级用户仍然使用下面的CLI工具来执行其他手动操作。