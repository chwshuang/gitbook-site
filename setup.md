# 安装和使用GitBook

完成GitBook的安装只需要几分钟。

### GitBook.com

[GitBook.com](https://www.gitbook.com)为您提供简单高效的图书在线撰写、发布和托管方案， 你可以通过[GitBook.com](https://www.gitbook.com)进行在线编辑、或者使用[GitBook 本地编辑器](https://www.gitbook.com/editor)在本地电脑上编辑。


### 本地安装

##### 要求

GitBook的安装非常简单。您的系统只需满足这两个要求：

* NodeJS（推荐使用v4.0.0及以上版本）
* Windows，Linux，Unix或Mac OS X

##### 使用NPM安装

安装GitBook的最好方法是通过 `NPM` 安装。在已经安装好NodeJS和NPM的电脑上，通过命令行窗口，输入以下命令安装GitBook：

```
$ npm install gitbook-cli -g
```

`gitbook-cli` 是安装和管理GitBook版本库的程序。它会自动安装GitBook所需的模块来创建一本书。

##### 创建一本书

GitBook通过以下命令在当前目录创建一本书：

```
$ gitbook init
```

如果你想用现有的目录来创建一本书，你可以通过运行 `gitbook init ./directory`来实现

使用下面的命令预览您创建的图书：

```
$ gitbook serve
```

或者使用以下命令构建静态网站：

```
$ gitbook build
```

##### 安装其他版本

`gitbook`命令可以方便地下载和安装不同版本的GitBook来测试你的书：

```
$ gitbook fetch 4.0.0-alpha.1
```

使用`gitbook ls-remote`列出可用于安装的远程版本。

```
$ gitbook ls-remote
Available GitBook Versions:

     4.0.0-alpha.5, ...部分省略..., 4.0.0-alpha.1, 3.2.2, 3.2.1, ...部分省略..., 2.0.0-alpha.1

Tags:

     latest : 3.2.2
     pre : 4.0.0-alpha.5
```


##### 调试

您可以使用`--log=debug`和`--debug`来获得更详细的错误消息（堆栈跟踪）。例如：

```
$ gitbook build ./ --log=debug --debug
```
or
```
$ gitbook serve ./ --log=debug --debug
```
