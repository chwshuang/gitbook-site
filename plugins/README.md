# 插件

插件是扩展GitBook功能(电子书和网站)的最佳方式。有插件做很多事情：使数学公式显示支持，使用Google Analytics(分析)跟踪访问等。

### 如何找到插件？

您可以在[plugins.gitbook.com](https://plugins.gitbook.com)轻松搜索插件。


### 如何安装插件？

一旦你找到你想要安装的插件，你需要将它添加到你的`book.json`：

```
{
    "plugins": ["myPlugin", "anotherPlugin"]
}
```

您还可以使用以下命令指定特定版本：`“myPlugin@0.3.1”`。默认不填写版本的情况下，GitBook使用最新版本（compatbile版本）的插件。

### GitBook.com

[GitBook.com](https://www.gitbook.com)上会自动帮你安装插件。如果是在本地环境，运行`gitbook install`来安装插件。

### 配置插件

插件的配置在`pluginsConfig`中。安装插件时，最好浏览插件的文档了解相关选项的详细信息。

