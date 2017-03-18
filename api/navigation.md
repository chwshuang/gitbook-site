# 导航

### 监听url的变化

监听当前位置的更改：


```js
const onLocationChanged = (location) => {
    console.log(location.pathname);
    console.log(location.query);
    console.log(location.hash);
};

module.exports = GitBook.createPlugin({
    init: (dispatch, getState, { Navigation }) => {
        dispatch(Navigation.listen(onLocationChanged));
    }
});
```

插件初始状态时`onLocationChanged`将被触发。

### 更改网址
