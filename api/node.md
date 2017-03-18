# 节点 API

GitBooks为插件提供了不同的节点 API和上下文。这些API可以根据使用的GitBook版本，你的插件应该在`package.json`中指定`engines.gitbook`字段。

#### Book实例

`Book`接口是GitBook的中心点，它集中了所有的访问读取方法。

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

#### 输出实例

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

#### 块和筛选器的上下文

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

#### 回调函数的上下文

回调函数只能使用`this.book`访问`<Book>`实例。

