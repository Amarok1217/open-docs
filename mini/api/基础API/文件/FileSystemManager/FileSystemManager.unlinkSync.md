
# 简介
[FileSystemManager.unlink](https://opendocs.alipay.com/mini/api/022b6p) 的同步版本。

## 使用限制

- 基础库 [2.7.4](https://opendocs.alipay.com/mini/framework/lib-upgrade-v2) 开始支持，低版本需要做 [兼容处理](https://docs.alipay.com/mini/framework/compatibility)。
- 此 API 支持个人支付宝小程序、企业支付宝小程序使用。

# 接口调用

## 示例代码

### .js 示例代码
```javascript
const fs = my.getFileSystemManager()
const result = fs.unlinkSync(`${my.env.USER_DATA_PATH}/test.txt`);
console.log(result);
```

## 入参

#### string filePath
文件路径。

## 错误码
| **错误码** | **说明** |
| --- | --- |
| 10022 | 文件不存在。 |
| 10023 | 传入的路径是一个目录。 |

