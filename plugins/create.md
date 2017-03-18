# 创建和发布插件

GitBook插件是在NPM上发布的遵循定义的约定的节点包。

## 结构体

#### package.json

`package.json`是用于描述**Node.js模块**的清单格式。 GitBook插件构建在Node模块之上。它声明了在GitBook中运行插件所需的依赖性，版本，所有权和其他信息。本文档详细描述了模式。

插件清单`package.json`还可以包含有关所需配置的详细信息。
在`package.json`中配置`gitbook`字段，需要遵循[JSON-Schema](http://json-schema.org)准则：

```js
{
    "name": "gitbook-plugin-mytest",
    "version": "0.0.1",
    "description": "This is my first GitBook plugin",
    "engines": {
        "gitbook": ">1.x.x"
    },
    "gitbook": {
        "properties": {
            "myConfigKey": {
                "type": "string",
                "default": "it's the default value",
                "description": "It defines my awesome config!"
            }
        }
    }
}
```

你可以从[NPM文档](https://docs.npmjs.com/files/package.json)了解更多关于`package.json`的内容。

**包名称**必须以`gitbook-plugin-`开头，**包引擎**应该包含`gitbook`。

#### index.js

`index.js`是插件运行时的入口：

```js
module.exports = {
    // Map of hooks
    hooks: {},

    // Map of new blocks
    blocks: {},

    // Map of new filters
    filters: {}
};
```

## 发布您的插件

GitBook插件可以在[NPM](https://www.npmjs.com)上发布。

要发布新插件，您需要在[npmjs.com](https://www.npmjs.com)上创建一个帐户，然后通过命令行发布：

```
$ npm publish
```

## 专用插件

专用插件可以托管在GitHub上，并使用`git` urls：

```
{
    "plugins": [
        "myplugin@git+https://github.com/MyCompany/mygitbookplugin.git#1.0.0"
    ]
}
```
