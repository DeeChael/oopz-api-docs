## 获取个人信息
GET: https://api.oopz.cn/client/v1/person/v1/selfDetail
参数：
```json5
{
    "uid": "" // 用户 UID，我也不知道为什么获取自己的信息为什么也要添加参数
}
```
回应：
```json5
{
    "status": true,
    "data": {
        "uid": "", // 用户的 UID
        "pid": "", // 不知道有什么作用的 ID
        "name": "", // 用户名
        "phone": "", // 手机号码
        "avatar": "", // 头像的链接
        "banner": "", // 头图的链接
        "online": true, // 是否在线
        "introduction": "", // 自我介绍
        "stealth": false, // 是否开启隐身状态
        "pwdSetTime": 0, // 不知道有什么用
        "mute": null, // 是否被禁言，但不在域中不知道有什么用
        "status": "ENABLED", // 未知
        "disabledStartTime": 0, // 未知
        "disabledEndTime": 0, // 未知
        "personType": "PERSON", // 猜测可能有 PERSON 和 BOT 两种类型
        "personRole": "NORMAL", // 人的角色，应该官方有不同的信息
        "personVIPStartTime": 0, // 用户 VIP 开通时间
        "personVIPEndTime": 0, // 用户 VIP 过期时间
        "areaMaxNum": 1, // 不知道
        "ipAddress": "", // IP 属地
        "defaultAvatar": false, // 是否使用默认头像
        "defaultName": false, // 是否使用默认名称
        "wxUnionId": "", // 不知道，跟微信有关
        "wxNickname": "", // 微信昵称
        "displayPlayingState": true, // 显示游玩状态
        "playingState": "", // 游玩状态
        "playingTime": 0, // 游戏时长
        "playingGameImage": "", // 游玩游戏的图片
        "badges": [], // 小图标，官方似乎有一个官人人员的 badge
        "userCommonId": "" // 和 pid 的值一样，不知道有什么用
    },
    "message": null,
    "error": null,
    "code": "200"
}
```