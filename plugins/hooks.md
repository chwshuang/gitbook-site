# 回调函数

回调函数通过自定义回调来增强或改变进程行为的方法。

### 回调函数列表

### 全局属性

|名称|说明|参数|
| ---- | ----------- | ---------
| `init` |在解析书之后，生成输出页面之前调用。 |无|
| `finish：before` |在生成输出页面后调用，在复制资源，生成封面之前调用 |无|
| `finish` |所有操作完成后调用。 |无|

### 相对于页面管道

> 建议使用[模板](../templating/README.md)来扩展页面解析。

|名称|说明|参数|
| ---- | ----------- | ---------
| `page:before` |在页上运行模板引擎之前调用|页面对象|
| `page` |在输出和索引页面之前调用。 |页面对象|

##### 页对象

```js
{
    // Parser named
    "type": "markdown",

    // File Path relative to book root
    "path": "page.md",

    // Absolute file path
    "rawpath": "/usr/...",

    // Title of the page in the SUMMARY
    "title": "",

    // Content of the page
    // Markdown/Asciidoc in "page:before"
    // HTML in "page"
    "content": "# Hello"
}
```

##### 添加标题的示例

在`page：before`钩子中，`page.content`是markdown/asciidoc内容。

```js
{
    "page:before": function(page) {
        page.content = "# Title\n" +page.content;
        return page;
    }
}
```

##### 替换一些html的示例

在`page`回调函数中，将`page.content`中`<b>`标签替换为`<strong>`。

```js
{
    "page": function(page) {
        page.content = page.content.replace("<b>", "<strong>")
            .replace("</b>", "</strong>");
        return page;
    }
}
```

### 异步操作

回调函数可以异步返回。

例如：

```js
{
    "init": function() {
        return writeSomeFile()
        .then(function() {
            return writeAnotherFile();
        });
    }
}
```
