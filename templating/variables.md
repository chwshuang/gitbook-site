# 变量

以下是书的解析和主题生成期间可用数据的参考。

### 全局变量

|变量|说明|
| -------- | ----------- |
| `book` | `book.json`的全书信息+配置设置。详情请参阅下文。 |
| `gitbook` | GitBook特定信息|
| `page` |当前页特定信息|
| `file` |与当前页特定信息相关联的文件|
| `readme` |自述相关内容|
| `glossary` |词汇相关内容|
| `summary` |菜单相关内容|
| `languages` |多语言书籍列表|
| `output` |输出相关内容|
| `config` |`book.json`相关内容 |

### 图书变量

|变量|说明|
| -------- | ----------- |
| `book.language` |多语言书的当前语言|
| `book.[value]`| 在`book.json`中的`variables`下的所有其他值都可以在这里访问|

例如，这个`book.json`：

```json
{
  variables: {
    hello: "everyone"
  }
}
```

...下面的文本 `{{ book.hello }}` 将会展开为 `everyone`。

### GitBook变量

|变量|说明|
| -------- | ----------- |
| `gitbook.time` |当前时间(当你运行`gitbook`命令时)。 |
| `gitbook.version` | GitBook用于生成图书的版本|

### 文件变量

|变量|说明|
| -------- | ----------- |
| `file.path` |原始页面的路径|
| `file.mtime` |修改时间。上次修改文件的时间|
| `file.type` |用于编译此文件的语法解析器的名称(例如：`markdown`，`asciidoc`等)|

#### 页面变量

|变量|说明|
| -------- | ----------- |
| `page.title` |页面标题|
| `page.previous` |内容表中的前一页(可以是“null”)|
| `page.next` |内容表中的下一页(可以是“null”)|
| `page.dir` |文本方向，基于配置(`rtl`或`ltr`)|

#### 目录变量

|变量|说明|
| -------- | ----------- |
| `summary.parts` |内容列表|

可以访问整个目录(`SUMMARY.md`)：

`summary.parts[0].articles[0].title`将返回第一篇文章的标题。

多语言环境变量

|变量|说明|
| -------- | ----------- |
| `languages.list` |本书的语言环境列表|

定义一种语言的方式：`{ id: 'en', title: 'English' }`。

### 输出变量

|变量|说明|
| -------- | ----------- |
| `output.name` |输出生成器的名称，可能的值是`website`，`json`，`ebook` |
| `output.format` |当`output.name ==“ebook”`，`format`定义将生成的电子书格式，可能的值是`pdf`，`epub`或`mobi` |

### 自述文件变量

|变量|说明|
| -------- | ----------- |
| `readme.path` |自述文件的路径|

### 词汇表变量

|变量|说明|
| -------- | ----------- |
| `glossary.path` |词汇表的路径|


