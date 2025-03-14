
# 简介
**my.hideLoading** 是隐藏加载提示的过渡效果的 API，可与 [my.showLoading](/mini/api/bm69kb) 配合使用。

## 使用限制
此 API 支持个人支付宝小程序、企业支付宝小程序使用。

# 接口调用

## Herbox
[小程序在线](https://herbox-embed.alipay.com/s/doc-loading?theme=light&previewZoom=75&chInfo=openhome-doc) 

## 示例代码

### .js 示例代码
```javascript
// .js
Page({
  onLoad() {
    my.showLoading();
    const that = this;
    setTimeout(() => {
      my.hideLoading({
        page: that,  // 防止执行时已经切换到其它页面，page 指向不准确
      });
    }, 4000);
  }
})
```

## 入参
Object 类型，属性如下：

| **属性** | **类型** | **必填** | **描述** |
| --- | --- | --- | --- |
| page | Object | 否 | 具体指当前 page 实例，某些场景下，需要指明在哪个 page 执行 hideLoading。  |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |

