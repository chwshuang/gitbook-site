# Context和APIs

GitBooks为插件提供了不同的API和上下文。这些API可以根据使用的GitBook版本，你的插件应该在`package.json`中指定`engines.gitbook`字段。

#### Book实例

`Book`类是GitBook的中心点，它集中了所有的访问读取方法。这个类在[book.js]（https://github.com/GitbookIO/gitbook/blob/master/book.js）中定义。

```js
//从book.json读取配置
var value = book.config.get（'title'，'Default Value'）;

//将文件名解析为绝对路径
var filepath = book.resolve（'README.md'）;

//呈现内联标记字符串
book.renderInline（'markdown'，'This is ** Markdown **'）
    .then（function（str）{...}）

//呈现标记字符串（块模式）
book.renderBlock（'markdown'，'*这是** Markdown **'）
    .then（function（str）{...}）
```

####输出实例

`Output`类代表输出/写入过程。

```js
//返回输出的根文件夹
var root = output.root（）;

//解析输出文件夹中的文件
var filepath = output.resolve（'myimage.png'）;

//将文件名转换为URL（返回html文件的路径）
var fileurl = output.toURL（'mychapter / README.md'）;

//在输出文件夹中写入一个文件
output.writeFile（'hello.txt'，'Hello World'）
    .then（function（）{...}）;

//将文件复制到输出文件夹
output.copyFile（'./ myfile.jpg'，'cover.jpg'）
    .then（function（）{...}）;

//验证文件是否存在
output.hasFile（'hello.txt'）
    .then（function（exists）{...}）;
```

####页面实例

页面实例表示当前已解析页面。

```js
//页面标题（摘自摘要）
页面标题

//页面内容（Markdown / Asciidoc / HTML根据阶段）
page.content

//书中的相对路径
page.path

//文件的绝对路径
page.rawPath

//用于此文件的解析器的类型
page.type（'markdown'或'asciidoc'）
```

####块和筛选器的上下文

块和过滤器可以访问相同的上下文，此上下文绑定到模板引擎执行：

```js
{
    //当前模板语法
    “ctx”：{
        //例如，在{％set message =“hello”％}之后
        “message”：“hello”
    }，

    // Book instance
    “book”，“

    //输出实例
    “output”：<Output>
}}
```

例如，过滤器或块函数可以使用：`this.book`访问当前书。

####钩子的上下文

钩子只能使用`this.book`访问`<Book>`实例。







# Context and APIs

GitBooks provides different APIs and contexts to plugins. These APIs can vary according to the GitBook version being used, your plugin should specify the `engines.gitbook` field in `package.json` accordingly.

#### Book instance

The `Book` class is the central point of GitBook, it centralize all access read methods. This class is defined in [book.js](https://github.com/GitbookIO/gitbook/blob/master/book.js).

```js
// Read configuration from book.json
var value = book.config.get('title', 'Default Value');

// Resolve a filename to an absolute path
var filepath = book.resolve('README.md');

// Render an inline markup string
book.renderInline('markdown', 'This is **Markdown**')
    .then(function(str) { ... })

// Render a markup string (block mode)
book.renderBlock('markdown', '* This is **Markdown**')
    .then(function(str) { ... })
```

#### Output instance

The `Output` class represent the output/write process.

```js
// Return root folder for the output
var root = output.root();

// Resolve a file in the output folder
var filepath = output.resolve('myimage.png');

// Convert a filename to an URL (returns a path to an html file)
var fileurl = output.toURL('mychapter/README.md');

// Write a file in the output folder
output.writeFile('hello.txt', 'Hello World')
    .then(function() { ... });

// Copy a file to the output folder
output.copyFile('./myfile.jpg', 'cover.jpg')
    .then(function() { ... });

// Verify that a file exists
output.hasFile('hello.txt')
    .then(function(exists) { ... });
```

#### Page instance

A page instance represent the current parsed page.

```js
// Title of the page (from SUMMARY)
page.title

// Content of the page (Markdown/Asciidoc/HTML according to the stage)
page.content

// Relative path in the book
page.path

// Absolute path to the file
page.rawPath

// Type of parser used for this file
page.type ('markdown' or 'asciidoc')
```

#### Context for Blocks and Filters

Blocks and filters have access to the same context, this context is bind to the template engine execution:

```js
{
    // Current templating syntax
    "ctx": {
        // For example, after a {% set message = "hello" %}
        "message": "hello"
    },

    // Book instance
    "book" <Book>,

    // Output instance
    "output": <Output>
}
```

For example a filter or block function can access the current book using: `this.book`.

#### Context for Hooks

Hooks only have access to the `<Book>` instance using `this.book`.
