# 目录结构

GitBook使用[SUMMARY](pages.md)文件管理目录结构，文件支持Markdown和Asciidoc两种语法。
GitBook按照[SUMMARY](pages.md)文件中的目录结构生成HTML。
如果你通过GitBook创建一本支持多语言文档，目录结构会稍微不同，具体可参考[多语言环境](languages.md)。

一般GitBook目录如下：

```
.
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```


简单介绍每一项：

|文件|说明|
| -------- | ----------- |
| `book.json` | 保存 [配置文件](config.md)数据(__可选__)|
| `README.md` |简介 - 书籍的简单介绍(**必填**)|
| `SUMMARY.md` |目录(参见[目录管理](pages.md))(__可选__)|
| `GLOSSARY.md` |字段/注释 - 专业术语列表(参见[词汇表](lexicon.md))(__可选__)|

### 静态文件

静态文件是在`SUMMARY.md`中未列出的文件。所有静态文件，包含图片、JS、CSS都会复制到对应目录下，

### 忽略的文件和文件夹

GitBook将读取`.gitignore`、`.bookignore`和`.ignore`文件，以获取要忽略的文件和文件夹的列表。被忽略的文件不会被上传到版本中。
这些文件中的格式遵循与`.gitignore`相同的约定：

```
＃井号代表这是一行注释

＃忽略文件test.md
test.md

＃忽略目录“bin”中的所有内容
bin/*
```

### 以子目录的方式与项目集成

对于软件项目，可以使用子目录(如`docs/`)来存储项目的文档。您可以在`book.json`中通过[配置](config.md)选项告诉GitBook在那里找到根目录：


```
.
├── book.json
└── docs/
    ├── README.md
    └── SUMMARY.md
```


`book.json` 中的配置如下：

```
{
    "root": "./docs"
}
```
