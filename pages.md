# 菜单与页面

---

### 菜单

GitBook使用一个`SUMMARY.md`文件来定义文档的菜单。 

`SUMMARY.md`中`[]`内的内容是标题，`()`内是文档的路径，章节和子章节用四个空格或者`tab`键来分级。


##### 简单示例

```markdown
# 概述

### 第一部分

* [第一部分](part1/README.md)
    * [Writing很牛](part1/README.md#writing)
    * [GitBook很牛](part1/README.md#gitbook)
* [第二部分](part2/README.md)
    * [我们喜欢社交网络](part2/README.md#feedback)
    * [更好的写作工具](part2/README.md#tools)
```

每一个章节都有一个专用的页面（`part1/README.md#`），并被分割成子章节。



##### 区域导航

文章可以使用区域导航定位到文件的特定部分。
在md文件结尾使用`#`号加上文章内容中章节的标题就能实现区域导航

```markdown
# 概述

### 第一部分

* [第一部分](part1/README.md)
    * [Writing很牛](part1/README.md#writing)
    * [GitBook很牛](part1/README.md#gitbook)
* [第二部分](part2/README.md)
    * [我们喜欢社交网络](part2/README.md#feedback)
    * [更好的写作工具](part2/README.md#tools)
```

##### 部分

内容表可以分为由标题或水平线分隔的部分：

```markdown
# 章节标题

这里是一些简单的介绍。

## 第一节

Markdown will dictates _most_ of your **book's structure**

## 第二节

...

```

部分只是章节组，没有对应的页面，但根据不同主题，它会显示在导航中。


---

### 页面


#### Markdown语法

GitBook默认使用Markdown语法编写页面。
Markdown语法可参考[GitBook Markdown语法](./syntax/markdown.md)章节。也可以选择[AsciiDoc语法](./syntax/asciidoc.md)。

##### 章节文件的示例

```markdown
＃本章标题

这里是介绍。

## 第1节

Markdown将决定 **书的结构**

## 第2节

... ...

```

#### 顶部描述

页面可以用它作为描述。
它使用`YAML`格式的风格，在三条虚线之间。
文档中也可以不写顶部描述。

> **特别提示**:在没有安装支持插件之前，不要在文件中使用，否则编译或者运行会失败。

这里有一个基本的例子：


```yaml
---
description: This is a short description of my page
---

# The content of my page
...
```

顶部描述的内容可以定义自己的变量，可以参考[页面变量](templating/variables.md)，以便您可以在模板中使用它们。

