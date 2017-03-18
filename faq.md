# GitBook常见问题

本页收集有关GitBook的常见问题和答案。

有关GitBook.com和编辑器的问题，请参阅[help.gitbook.com的常见问题](http://help.gitbook.com/faq.html)。

---

#### 如何托管/发布我的图书？

图书可以轻松地在[GitBook.com](https://www.gitbook.com)上发布和托管。GitBook输出的静态文件也支持其他托管解决方案。

#### 我可以使用哪些功能编辑我的内容？

任何文本编辑器都可以！但我们建议使用[GitBook 编辑器](https://www.gitbook.com/editor)。 [GitBook.com](https://www.gitbook.com)网站上还提供了此编辑器的在线版本。

---

#### GitBook是否支持文本右对齐、两端对齐？

GitBook支持文本右对齐，包括两端对齐。要启用它，你需要在`book.json`指定一种语言(例如：`zh`)，并设置它的对齐方式：

```json
{
    “language"："zh"，
    “direction"："rtl"
}
```

如果你使用版本是3.0及以上的GitBook，它会根据内容自动检测。

_注意，虽然书和文档的格式会按照你设置的文本对齐方式输出，但在编辑器中编辑文本的时候是不会按照这个设置显示。_


#### 我应该在链接中使用`.html` 或者 `.md`扩展名吗？

链接到文件时，应始终使用路径和`.md`扩展名，目录中引用指向文件时，GitBook会通过相应的链接自动替换这些路径。

#### 我可以在我的项目的子目录中创建一个GitBook吗？

是的，GitBooks可以在[子目录](structure.md#subdirectory)中创建。GitBook.com和CLI会默认查看所有的[文件夹](structure.md)。

#### GitBook是否支持RTL(对齐)语法？

是的，GitBook自动检测您的页面中的方向(`rtl`或`ltr`)，并调整布局。方向也可以在全局配置文件[book.json](config.md)中指定。

---

#### GitBook是否支持数学方程式？

GitBook需要安装插件来支持数学方程式。目前有2个官方插件来显示数学方程式：[mathjax](https://plugins.gitbook.com/plugin/mathjax)和[katex](https://plugins.gitbook.com/plugin/katex)。

#### 可以自定义主题吗？

可以，你可以查看[主题](themes/README.md)段落学习如何自定义主题。

#### 我可以添加交互式内容吗(视频等)？

GitBook是[可扩展的](plugins/README.md)。你可以参考[插件](https://plugins.gitbook.com)中的说明来创建属于自己的内容！

