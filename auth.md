## 自动登录
POST: https://api.oopz.cn/client/v1/login/v1/autoLogin

参数：
```json
{
    "auto": true,
    "code": "", // 登录代码
    "loginType": "SIGNATURE", // 登录类型
    "phone": "", // 电话号码
    "autoRegister": false,
    "deviceId": "", // 设备 ID
    "deviceRam": "", // 作用未知
    "deviceProcessor": "0",
    "loggedIn": "", // 大部分情况和 deviceId 一致
    "osEdition": "web",
    "osVersion": "web",
    "resolution": "", // 未知
    "graphics": "", // 未知
    "clientVersion": "0.15.59" // 客户端版本
}
```
响应：
```json
{
    "status": true,
    "data": {
        "uid": "", // 用户 UID
        "stealth": false,
        "signature": "", // 签名，调用 API 获取信息需要用到这个
        "status": "ENABLED",
        "disabledStartTime": 0,
        "disabledEndTime": 0,
        "name": "" // 用户名
    },
    "message": null,
    "error": null,
    "code": "200"
}
```