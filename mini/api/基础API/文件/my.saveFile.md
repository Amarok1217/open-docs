
# 简介
**my.saveFile** 是保存文件到本地（本地文件大小总容量限制：10 MB）的 API。

## 使用限制

- 基础库 [1.13.0](https://opendocs.alipay.com/mini/framework/lib)  或更高版本，支付宝客户端 10.1.32 或更高版本，若版本较低，建议采取 [兼容处理](/mini/framework/compatibility)。
- 此 API 支持个人支付宝小程序、企业支付宝小程序使用。

## 扫码体验
![|127x157](https://gw.alipayobjects.com/zos/skylark-tools/public/files/3a76443909a425c37fec24b43b6bcd85.jpeg#align=left&display=inline&height=157&margin=%5Bobject%20Object%5D&originHeight=157&originWidth=127&status=done&style=stroke&width=127)

## 效果示例
![|370x664](http://mdn.alipayobjects.com/afts/img/A*WbFmS5eMqjAAAAAAAAAAAAAAAa8wAA/original?bz=openpt_doc&t=dKNiQT8PMtRU65WBY5c6bAAAAABkMK8AAAAA#align=left&display=inline&height=664&margin=%5Bobject%20Object%5D&originHeight=664&originWidth=370&status=done&style=stroke&width=370)

# 接口调用

## 示例代码

### .js 示例代码
```javascript
// .js
my.chooseImage({
  success: (res) => {
    my.saveFile({
      apFilePath: res.apFilePaths[0],
      success: (res) => {
        console.log(JSON.stringify(res))
      },
    });
  },
});
```

## 入参
Object 类型，属性如下：

| **属性** | **类型** | **必填** | **描述** |
| --- | --- | --- | --- |
| apFilePath | String | 是 | 文件路径。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |


### success 回调函数
| **属性** | **类型** | **描述** |
| --- | --- | --- |
| apFilePath | String | 文件保存路径。 |

