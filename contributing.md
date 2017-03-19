# 参与贡献

非常感谢你参与Gitbook的贡献！

## 发送反馈

如果您在使用GitBook工作的时候，有一些使用上的问题，
我们的产品虽然有很完善的测试来保证质量，但是不能绝对避免您在使用GitBook的时候遇到一些问题，这个时候，需要你到了[GitbookIO/feedback](https://github.com/GitbookIO/feedback/issues) 频道来提交你使用产品时的一些反馈。


## 错误报告

如果您使用GitBook的时候，遇到任何异常的情况，可以随时在这个文档中提交一个新的问题！在提交问题的时候能通过`gitbook -V`告诉我们一些版本的信息是最好不过了。
```bash
$ gitbook -V
CLI version: 2.3.0
GitBook version: 3.2.2
```

## 提问

提交问题的时候，可以到[`question`](https://github.com/GitBookIO/gitbook/issues?q=is%3Aissue+is%3Aclosed+label%3Aquestion)标签页看看有没有相同的提问，如果找不到，您可以创建一个新的提问！

你也可以到[GitBook社区](https://slack.gitbook.com/) 提出问题，在这里，你或许可以从其他人那里得到你想要的答案！


## 提交请求

我们非常欢迎你提交请求! 如果你想简单了解代码，从我们提供的 [`easy-one`](https://github.com/GitBookIO/gitbook/issues?q=is%3Aopen+is%3Aissue+label%3Aeasy-one) 标签页来做一些简单的任务，加深对代码的了解。

提交的请求最好包含每次的测试文件！

## 运行测试

要运行项目，需要将gitbook库克隆到本地，然后进入项目目录，先使用 `npm` 或者 `yarn` 安装依赖。

```
$ yarn install
```

然后启动:

```
$ npm run bootstrap
```

上一步将编译源文件，接着就可以运行测试:

```
$ npm test
```