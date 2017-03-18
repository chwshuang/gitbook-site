# 连接到上下文

`GitBook.connect（Component，[mapStateToProps]，[mapActionsToProps]）`将react组件连接到GitBook上下文。

它不修改传递给它的组件类。
相反，它返回一个新的，连接的组件类，供您使用。

### `mapStateToProps（state，[ownProps]）：stateProps`

如果指定，组件将订阅GitBook存储更新。任何时候更新，`mapStateToProps`将被调用。它的结果必须是一个简单的对象，它将被合并到组件的道具中。

如果省略它，组件将不会订阅GitBook存储。如果`ownProps`被指定为第二个参数，它的值将是传递给你的组件的道具，`mapStateToProps`将会在组件接收到新的道具时被额外重新调用（例如，如果从父组件接收到的道具浅浅地改变了，你使用`ownProps`参数，`mapStateToProps`被重新计算）。

例如要渲染当前页面的标题：

```js
const GitBook = require('gitbook-core');

let PageTitle = React.createClass({
    render() {
        const { page } = this.props;
        return <h1>{page.title}</h1>;
    }
});

function mapStateToProps(state) {
    return { page: state.page };
}

PageTitle = GitBook.connect(PageTitle, mapStateToProps);
```

/### `mapActionsToProps(actions, [dispatch])`


