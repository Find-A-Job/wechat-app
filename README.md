# wechat-app
---

### .json
```
// 复制的时候要去掉注释，json里不允许注释
{
  "usingComponents": {},
  // 自定义导航栏
  "navigationStyle":"custom",
  // 禁止下拉、上滑
  "disableScroll": true
}
```

### .js
```
  queryPropAwait: function (params) {
    var retVal = {}; //这里需要用分号隔开，要不然解释器会误认为和下面的()是一条语句
    (async () => {
      let result = await new Promise((resolve, reject) => {
        query.select(params.select)
          .fields(params.fields)
          .exec((res) => {
            resolve(res[0])
          })
      });
      // console.log('output', size, position)
      retVal = result
      //后续语句应在此处继续
    })();
    // 后面执行的其他代码并不等待上面的箭头函数执行完成
    // ...
  },
```

### .wxml
```

```

### .wxss
```

```

### 其他
* wxss的transform属性生效发生在onReady之后,也就是说在onReady里获取不到到节点的最终状态
```

```
