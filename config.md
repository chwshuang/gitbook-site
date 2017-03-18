# 配置

GitBook允许您使用灵活的配置自定义书籍和文档。这些选项在`book.json`文件中指定。对于不熟悉JSON语法的作者，您可以使用[JSONlint](http://jsonlint.com)等工具验证语法。

### 常规设置

|变量|说明|
| -------- | ----------- |
| `root` |包含所有图书文件的根文件夹的路径，除了`book.json` |
| `structure` |指定自述，摘要，词汇表等的路径。请参见[结构段落](＃结构)。 |
| `title` |书的标题，默认值从README中提取。在GitBook.com上，此字段已预填。 |
| `description` |您的图书说明，默认值从自述文件中提取。在GitBook.com上，此字段已预填。 |
| `author` |作者姓名。在GitBook.com上，此字段已预填。 |
| `isbn` |书的国际码ISBN|
| `language` | [语言ISO规范](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)的书的语言，默认值是`en` |
| `direction` |文本的方向。可以是`rtl`或`ltr`，默认值取决于`language` 的值|
| `gitbook` |GitBook的版本。使用[SemVer](http://semver.org)规范并接受诸如`“> = 3.0.0”`的条件|

### 插件

插件及其配置在`book.json`中指定。有关更多详细信息，请参阅[插件部分](plugins/README.md)。

从3.0.0版本开始，GitBook可以使用主题。有关详细信息，请参阅[主题部分](themes/README.md)。

|变量|说明|
| -------- | ----------- |
| `plugins` |要加载的插件列表|
| `pluginsConfig` |插件配置|

### 结构体

除了`root`变量，你可以告诉Gitbook Readme，Summary，Glossary，Languages的文件名(而不是使用默认名称，如README.md)。
这些文件必须在您的书的根(或每个语言书的根)。不接受诸如`dir/MY_README.md`之类的路径。

|变量|说明|
| -------- | ----------- |
| `structure.readme` |自述文件名(默认为“README.md”)|
| `structure.summary` |摘要文件名(默认为“SUMMARY.md”)|
| `structure.glossary` |词汇表文件名(默认为“GLOSSARY.md”)|
| `structure.languages` | 语言文件名(默认为`LANGS.md`)|

### PDF选项

PDF输出可以使用`book.json`中的一组选项来定制：

|变量|说明|
| -------- | ----------- |
| `pdf.pageNumbers` |将页码添加到每个页面的底部(默认为“true”)|
| `pdf.fontSize` |基本字体大小(默认为`12`)|
| `pdf.fontFamily` |基本字体系列(默认为`Arial`)|
| `pdf.paperSize` |纸张大小，选项为“a0”，“a1”，“a2”，“a3”，“a4”，“a5”，“a6”，“b0”，“b1”，“b2”，“b3” 'b4'，'b5'，'b6'，'legal'，'letter''(默认为'a4')|
| `pdf.margin.top`|顶部边距(默认为`56`)|
| `pdf.margin.bottom` |底边距(默认为`56`)|
| `pdf.margin.right` |右边距(默认为“62”)|
| `pdf.margin.left` |左边距(默认为“62”)|
