# 模板

GitBook使用[Nunjucks模板语言](https://mozilla.github.io/nunjucks/)来处理页面和主题的模板。

Nunjucks语法与**Jinja2**或**Liquid**非常相似。语法使用大括号`{}`来标记需要处理的内容。

### 变量

变量从模板上下文中查找值。如果你想简单地显示一个变量，你可以使用`{{variable}}`语法。例如 ：

```twig
我的名字是{{ name }}，很高兴见到你
```

它从上下文中查找用户名并显示它。变量名称在其中可以有点像查找属性，就像JavaScript。您还可以使用方括号语法。

```twig
{{ foo.bar }}
{{ foo["bar"] }}
```

如果值未定义，则不显示任何内容。如果foo未定义，下面的所有输出都不会输出：`{{ foo }}`, `{{ foo.bar }}`, `{{ foo.bar.baz }}`。

GitBook提供了[预定义变量](variables.md)。

### 过滤器

过滤器本质上是可以应用于变量的函数。它们用管道操作符(`|`)调用，并且可以接受参数。

```twig
{{ foo | title }}
{{ foo | join(",") }}
{{ foo | replace("foo", "bar") | capitalize }}
```


第三个例子显示了如何链式使用过滤器。首先用“bar”替换“foo”，然后将其大写，最后输出为“Bar”，。

### 条件判断

##### if

`if` 根据条件选择显示内容。它的行为与JavaScript的`if`行为完全一样。


```twig
{% if variable %}
  It is true
{% endif %}
```

如果变量被定义并且计算结果为true，将显示“It is true”。否则，什么都不会。

您可以使用`elif`和`else`指定替代条件：

```twig
{% if hungry %}
  I am hungry
{% elif tired %}
  I am tired
{% else %}
  I am good!
{% endif %}
```

##### for

`for`遍历数组和对象。

```twig
# Chapters about GitBook

{% for article in glossary.terms['gitbook'].articles %}
* [{{ article.title }}]({{ article.path }})
{% endfor %}
```

##### set

`set`允许你创建/修改一个变量。

```twig
{% set softwareVersion = "1.0.0" %}

Current version is {{ softwareVersion }}.
[Download it](website.com/download/{{ softwareVersion }})
```

##### 内容引用

请查看[内容引用](conrefs.md)部分中的说明。

### 原始输出

使用raw可以将内容作为纯文本输出，模板和标签的格式也会一样。

```twig
{% raw %}
  this will {{ not be processed }}
{% endraw %}
```


