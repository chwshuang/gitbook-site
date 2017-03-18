# 过滤器

过滤器本质上是可以应用于变量的函数。它们用管道操作符(`|`)调用，并且可以接受参数。

```
{{ foo | title }}
{{ foo | join(",") }}
{{ foo | replace("foo", "bar") | capitalize }}
```

### 定义一个新的过滤器

可以在过滤器的入口自定义函数来扩展过滤器。

过滤器函数将要过滤的内容作为第一个参数，并应返回新内容。
参考[上下文API](../api/README.md)了解更多关于`this`和GitBook API。

```js
module.exports = {
    filters: {
        hello: function(name) {
            return 'Hello '+name;
        }
    }
};
```

过滤器`hello`然后可以在书中使用：

```
{{ "Aaron"|hello }}, how are you?
```

### 处理块参数

参数可以传递到过滤器：

```
Hello {{ "Samy"|fullName("Pesse", man=true}} }}
```

参数传递给函数，命名参数作为最后一个参数(对象)传递。

```js
module.exports = {
    filters: {
        fullName: function(firstName, lastName, kwargs) {
            var name = firstName + ' ' + lastName;

            if (kwargs.man) name = "Mr" + name;
            else name = "Mrs" + name;

            return name;
        }
    }
};
```
