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
  // 属性查询 改进版 用await等待结果返回
  queryPropAwait: function (params) {
    // params.select
    // params.fields
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
    })();
    return retVal
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
