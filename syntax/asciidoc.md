# AsciiDoc

从`2.0.0`版本开始，GitBook接受AsciiDoc语法文件作为输入格式。

有关格式的更多信息，请参阅[AsciiDoc语法快速参考](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/)。

跟markdown一样，GitBook可以从下的面文件来提取结构：README.adoc，SUMMARY.adoc，LANGS.adoc和GLOSSARY.adoc。

### README.adoc

这是你的文档或者书籍的主要入口：此文件是 **必填**。

### SUMMARY.adoc

“SUMMARY.adoc”是菜单列表，链接的名称用作章节的名称，目标是该章节文件的路径。

通过向父章节添加嵌套列表来定义子章节。

```asciidoc
=菜单

. link:chapter-1/README.adoc[Chapter 1]
.. link:chapter-1/ARTICLE1.adoc[Article 1]
.. link:chapter-1/ARTICLE2.adoc[Article 2]
... link:chapter-1/ARTICLE-1-2-1.adoc[Article 1.2.1]
. link:chapter-2/README.adoc[Chapter 2]
. link:chapter-3/README.adoc[Chapter 3]
. link:chapter-4/README.adoc[Chapter 4]
.. Unfinished article
. Unfinished Chapter
```

### LANGS.adoc

对[多语言](../languages.md)书籍，此文件用于定义不同的支持语言。

此文件遵循与SUMMARY.adoc相同的语法：

```asciidoc
= Languages

. link:en/[English]
. link:fr/[French]
```

### GLOSSARY.adoc

此文件用于定义术语或者词汇表。 [见词汇表部分](../lexicon.md)。

```asciidoc
= Glossary

== Magic

Sufficiently advanced technology, beyond the understanding of the
observer producing a sense of wonder.

== PHP

A popular web programming language, used by many large websites such
as Facebook. Rasmus Lerdorf originally created PHP in 1994 to power
his personal homepage (PHP originally stood for "Personal Home Page"
but now stands for "PHP: Hypertext Preprocessor").
```
