# JS 格式化数值让其以保留两位小数

price需要保留两位小数

![image-20211130014555231](/Users/jiaxi.gong/Library/Application Support/typora-user-images/image-20211130014555231.png)

### 相关错误

```javascript
const formatPrice = parseFloat(props.price).toFixed(2) || 0.0;
```

1.数字才有toFix方法。所以如果其他组件引用该组件，在测试时因为mock的都是字符串，所以会报toFixed is not a function错误

<img src="/Users/jiaxi.gong/Library/Application Support/typora-user-images/image-20211130015010841.png" alt="image-20211130015010841" style="zoom:50%;" />

2.同样很多测试时测试用例不全，会报没有该属性的错误

<img src="/Users/jiaxi.gong/Library/Application Support/typora-user-images/image-20211130015210940.png" alt="image-20211130015210940" style="zoom:50%;" />

fdjsaiofjdasoij