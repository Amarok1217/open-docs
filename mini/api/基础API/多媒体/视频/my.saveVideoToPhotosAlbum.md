
# 简介
保存视频到系统相册。

## 使用限制

- 基础库 [1.10.0](https://opendocs.alipay.com/mini/framework/lib) 开始支持，低版本需要做 [兼容处理](https://docs.alipay.com/mini/framework/compatibility)。
- 此 API 暂仅支持企业支付宝小程序使用。
- 开发者工具暂不支持此能力，请使用 [真机调试](https://opendocs.alipay.com/mini/ide/remote-debug) 功能在真机进行调试。

# 接口调用

## 示例代码

### .js 示例代码
```javascript
// 本地路径
my.chooseVideo({
  sourceType: ['album','camera'],
  maxDuration: 60,
  camera: 'back',
  success(res) {
    my.saveVideoToPhotosAlbum({
     filePath: res.tempFilePath,
      complete(res2) {
       console.log(res2);
      }
    });
  }
})
// 网络路径
my.saveVideoToPhotosAlbum({
  filePath:'http://flv.bn.netease.com/tvmrepo/2012/7/C/7/E868IGRC7-mobile.mp4',
  complete(res) {
    console.log(res);
  }
});
```

## 入参
Object 类型，属性如下：

| **属性** | **类型** | **必填** | **描述** |
| --- | --- | --- | --- |
| filePath | String | 是 | 视频文件路径，支持本地路径或网络路径。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |


### 错误码
| **错误码** | **说明** |
| --- | --- |
| 2 | 参数无效，没有传 filePath 参数。 |
| 15 | 没有开启相册权限(iOS only)。 |
| 16 | 手机相册存储空间不足(iOS only)。 |
| 17 | 保存图片过程中的其他错误。 |

