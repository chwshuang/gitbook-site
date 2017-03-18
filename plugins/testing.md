# 测试您的插件

### 在本地测试你的插件

使用[npm link](https://docs.npmjs.com/cli/link)可以在发布之前测试你的插件。

在插件的文件夹中，运行：

```
$ npm link
```

然后在您的书或者文档的文件夹中执行：

```
$ npm link gitbook-plugin-<plugin's name>
```

### Travis的单元测试

[gitbook-tester](https://github.com/todvora/gitbook-tester)可以方便地为你的插件编写**Node.js/Mocha**单元测试。 使用[Travis.org](https://travis.org)，可以对每个提交/标签运行测试。

