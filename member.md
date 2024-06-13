## 列出一个域里的所有成员

GET：https://api.oopz.cn/area/v2/members

参数：

| 名称        | 类型   | 内容解释 | 参考值 |
| ----------- | ------ | -------- | -------- |
| area        | string | 域 ID    | 太好理解就不做展示 |
| offset | 区间 | 偏移量，即要列出多少用户 | 0-49：意为第1-50的用户，不确定排序方法，可能是加入时间 |

响应：

```json
{
    "status": true,
    "data": {
        "userCount": 2, // 用户总数
        "onlineCount": 1, // 在线的数量
        "offlineCount": 1, // 不在线的数量
        "members": [ // 成员列表
            [
                {
                    "person": "3603d653079011efa12c0aacbd5b115a", // 用户的 UID（这个是我的 UID）
                    "role": "e0bc5fe827b511efa0850afcb52f2a9b", // 角色的 ID（很不满意的一点，oopz 每个人只能有一个角色）
                    "level": 1, // 应该是角色的权力等级吧？
                    "online": true, // 是否在线
                    "playingState": "" // 正在游玩的游戏
                }
            ]
        ]
    },
    "message": null,
    "error": null,
    "code": "200"
}
```

