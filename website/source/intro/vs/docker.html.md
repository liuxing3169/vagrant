---
layout: "intro"
page_title: "Vagrant vs. Docker"
sidebar_current: "vs-docker"
description: |-
  Vagrant and Docker both provide isolation primitives. This page details the
  differences between them.
---

# Vagrant vs. Docker

Vagrant是一个专注于在多个操作系统上提供一致的开发环境工作流程的工具。 Docker是容器管理，只要容器化系统存在，就可以一直运行软件。

容器通常比虚拟机更轻便，因此启动和停止容器非常快。 大多数常见的开发机器没有内置的容器化系统，Docker使用安装了Linux的虚拟机来提供。

目前，Docker缺乏对某些操作系统（如BSD）的支持。 如果您的目标部署是这些操作系统之一，则Docker将不会像Vagrant这样的工具提供相同的生产平价。 Vagrant将允许您在Mac或Linux上运行Windows开发环境。

对于微服务重型环境，Docker很具吸引力，因为您可以轻松启动单个Docker VM，并快速启动很多容器。 这是使用Docker来说是一个很好的用例。 Vagrant也可以与Docker提供商一起做到这一点。 Vagrant的主要优点是一致的工作流程，但是在许多情况下，纯Docker工作流程确实有意义。

Vagrant和Docker都有一个的社区贡献的可供选择“images”或“boxes”的仓库。