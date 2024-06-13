## 密码登录

POST：https://api.oopz.cn/client/v1/login/v1/login

参数：

```json
{
	"auto": true,
	"code": "", // 密码内容
	"loginType": "PASSWORD", // 登录类型，下面还有验证码的
	"phone": "", // 手机号
	"autoRegister": true, // 自动注册，但我觉得这个在密码登录下不会起效果
	"deviceId": "", // 设备 id，我不知道这个是怎么生成的
	"deviceRam": "", // IDK
	"deviceProcessor": "", // IDK
	"loggedIn": "", // 应该指的是登录的设备，和 deviceId 的值一样
	"osEdition": "web", // 系统版本
	"osVersion": "web", // 系统版号
	"resolution": "", // 分辨率？
	"graphics": "", // 显卡？
	"clientVersion": "0.20.99" // 客户端版本
}
```

响应（失败）：

```json
{
    "status": false,
    "data": {
        "type": "ERROR_PASSWORD", // 类型
        "startTime": 0, // IDK
        "endTime": 0 // IDK
    },
    "message": "密码错误",
    "error": null,
    "code": "ERR.008.00005"
}
```

响应（成功）：

```json
{
    "status": true,
    "data": {
        "uid": "", // 用户的 UID
        "stealth": false,
        "signature": "", // 这是签名信息，请妥善保存防止泄露
        "status": "ENABLED",
        "disabledStartTime": 0,
        "disabledEndTime": 0,
        "name": "d6"
    },
    "message": null,
    "error": null,
    "code": "200"
}
```



## 验证码登录

获取验证码之前需要人机验证，无法绕过，所以我只能教之后的步骤了

POST：https://api.oopz.cn/client/v1/sms/v1/sendSmsCode 获取验证码

参数：

```json
{
	"phone": "", // 电话号码
	"randStr": "", // 随机字符，可能和人机验证有关
	"ticket": "" // 人机验证的码
}
```

无响应

下一步骤：登录

```json
{
	"auto": true,
	"code": "", // 验证码内容
	"loginType": "SMSCODE",
	"phone": "", // 手机号
	"autoRegister": true, // 自动注册
	"deviceId": "", // 设备 id，我不知道这个是怎么生成的
	"deviceRam": "", // IDK
	"deviceProcessor": "", // IDK
	"loggedIn": "", // 应该指的是登录的设备，和 deviceId 的值一样
	"osEdition": "web", // 系统版本
	"osVersion": "web", // 系统版号
	"resolution": "", // 分辨率？
	"graphics": "", // 显卡？
	"clientVersion": "0.20.99" // 客户端版本
}
```

响应参考密码登录

## 自动登录

POST: https://api.oopz.cn/client/v1/login/v1/autoLogin

参数：
```json
{
    "auto": true,
    "code": "", // 登录代码，使用上方任意一种方法登录后可以获取到签名，然后妥善保存好，再下次访问前可以使用此接口来验证签名是否过期。
    "loginType": "SIGNATURE", // 登录类型
	"phone": "", // 手机号
    "autoRegister": false,
	"deviceId": "", // 设备 id，我不知道这个是怎么生成的
	"deviceRam": "", // IDK
	"deviceProcessor": "", // IDK
	"loggedIn": "", // 应该指的是登录的设备，和 deviceId 的值一样
	"osEdition": "web", // 系统版本
	"osVersion": "web", // 系统版号
	"resolution": "", // 分辨率？
	"graphics": "", // 显卡？
	"clientVersion": "0.20.99" // 客户端版本
}
```
响应参考密码登录