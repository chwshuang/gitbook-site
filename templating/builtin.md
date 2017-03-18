# 模板助手

GitBook提供了一个内置过滤器和块来帮助您编写模板。

### 过滤器

`value|default(default, [boolean])`
值如果未定义，则返回默认值，否则返回值。 如果boolean为true，任何JavaScript falsy值将返回默认值(false，"", 等)

`arr|sort(reverse, caseSens, attr)`
使用JavaScript的arr.sort函数排序数组。 如果reverse为true，则结果将被反转。 默认情况下，排序不区分大小写，但将caseSens设置为true会使它区分大小写。 最后会比较数组中每个元素的的大小。

### 块

`{% markdown %}Markdown string{% endmarkdown %}`
渲染内联markdown

`{% asciidoc %}AsciiDoc string{% endasciidoc %}`
呈现内联asciidoc

