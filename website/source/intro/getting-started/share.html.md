---
layout: "intro"
page_title: "分析 - 开始使用"
sidebar_current: "gettingstarted-share"
description: |-
  Now that we have a web server up and running and accessible from your machine,
  we have a fairly functional development environment. But in addition to
  providing a development environment, Vagrant also makes it easy to share
  and collaborate on these environments. The primary feature to do this in
  Vagrant is called Vagrant Share.
---

# 分享

现在我们有了一个Web服务器已经启动并运行着，可以从你的电脑访问这个站点，还有一个我们非常熟悉的开发环境。
但除了提供开发环境外，Vagrant还让分享和贡献这些环境非常简单。在Vagrant中做这件事的主要功能叫做[Vagrant分享](/docs/share/)。

Vagrant分享功能让你可以通过互联网分享你的Vagrant环境给世界上的任何人。它将为您提供一个URL，该网址将直接从连接到互联网的世界上的任何设备路由到您的Vagrant环境。

运行 `vagrant share`:

```
$ vagrant share
...
==> default: Creating Vagrant Share session...
==> default: HTTP URL: http://b1fb1f3f.ngrok.io
...
```

你的URL将会不一样，所以不要尝试上面的URL。而是复制`vagrant share`输出的URL，并在Web浏览器中访问这个地址。它将加载我们早前建立起的Apache页面。

如果你在你的共享文件夹中修改文件并刷新URL，你将会看到它会更新！这个URL是定向到你的Vagrant环境的路由，并可以通过internet网络从世界上的任何设备上进行访问。

要结束分享回话，在终端中输入`Ctrl+C` 。你再一次可以刷新URL以验证你的环境不再被分享中。

Vagrant分享比简单的HTTP分享要强大的多。了解更多细节，请看[完整的Vagrant分享文档](/docs/share/)。

~> **Vagrant分享不是为生产场景所设计！** 请不要在开发环境之外依赖Vagrant分享或者问答。Vagrant分享不是为承载生产级别的流量所设计的。

## 下一步

你已经成功把你的环境分享给了全世界。恭喜! 继续阅读以了解更多关于[拆除处理](/intro/getting-started/teardown.html)。
