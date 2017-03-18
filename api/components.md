# 组件


## 注入

插件可以通过将React组件注册到`role`来注入组件。

#### 注册组件

插件初始化阶段，调用`GitBook.registerComponent`注册新组件：

```js
dispatch(GitBook.registerComponent(MyCustomButton, { role: 'toolbar:buttons:left' }));
```



#### 角色
自定义角色可以用于与其他插件的交互，但GitBook和默认主题设置了常见角色的约定：

| Role | Description | Props |
| ---- | ----------- | ----- |
| `page:container` | DIV container for the page's content | `{ page: Page }` |
| `summary:container` | DIV container for the whole summary | `{ summary: Summary }` |
| `summary:parts` | DIV container for summary's parts | `{ parts: List<SummaryPart> }` |
| `summary:part` | DIV for a specific part | `{ part: SummaryPart }` |
| `summary:articles` | UL container for a part's articles | `{ articles: List<SummaryArticle> }` |
| `summary:article` | LI for a specific article | `{ article: SummaryArticle }` |

## Default Components

#### `GitBook.Head`

扩展页面的元标记。 这是[react-helmet](https://github.com/nfl/react-helmet)的别名。

```js
<GitBook.Head
    title="My page"
  />
```

#### `GitBook.ImportCSS`

根据当前页面相对路径，导入CSS文件：

```js
<GitBook.ImportCSS href="myfile.css" />
```

#### `GitBook.InjectedComponent`

注入与特定角色匹配的组件：

```js
<GitBook.InjectedComponent matching={{ role: 'mycustomrole' }} props={{ someProp: 1 }}>
    <b>Inner content</b>
</GitBook.InjectedComponent>
```

#### `GitBook.InjectedComponentSet`

某些类似`InjectedComponentSet`的API用来匹配元件，而不是组成：

```js
<GitBook.InjectedComponentSet matching={{ role: 'mytoolbar' }} />
```

**警告:** 子项将失效.

#### `GitBook.FlexLayout` and `GitBook.FlexBox`

一个简单的包装器，提供给定方向和样式的Flexbox布局。 您在Flexbox上设置的任何其他道具都会呈现。

```js
<GitBook.FlexLayout column>
    <GitBook.FlexBox>First column</GitBook.FlexBox>
    <GitBook.FlexBox>Second column</GitBook.FlexBox>
</GitBook.FlexLayout>
```
