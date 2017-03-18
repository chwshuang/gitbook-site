# 内容引用

内容引用可以重用文件或书籍内容的一种的机制。

### 导入本地文件

使用`include`标记可以轻松导入其他文件的内容：

```
{% include "./test.md" %}
```

### 从另一本书中导入文件

GitBook也可以使用git解析包的路径：

```
{% include "git+https://github.com/GitbookIO/documentation.git/README.md#0.0.1" %}
```

git url的格式是：

```
git+https://user@hostname/owner/project.git/file#commit-ish
```

真正的git url部分应该用`.git`结尾，导入的文件名在`.git`之后被提取，直到url的片段。

`commit-ish`是引用项目的分支。默认为`master`。

### 继承

模板继承是一种方便重用的方法。在编写模板时，定义子模板可以覆盖父模板的"blocks"。

`block`定义模板上的一个部分，并用一个名字来标识它。基本模板可以指定块，子模板可以用新内容覆盖它们。

```
{% extends "./mypage.md" %}

{% block pageContent %}
# This is my page content
{% endblock %}
```

在`mypage.md`中，你应该指定可以扩展的块：


```
{% block pageContent %}
This is the default content
{% endblock %}

# License

{% include "./LICENSE" %}
```
