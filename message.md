## 列出消息
GET: https://api.oopz.cn/client/v1/list/v1/message

响应示例：由于我没有消息，所以不知道 data 里有什么。

## 发送消息

POST：https://api.oopz.cn/rtc/v1/gim/v1/sendText

参数：

```json
{
	"area": "", // 域 ID
	"channel": "", // 频道 ID
	"target": "", // 不知道有什么用
	"clientMessageId": "", // 客户端消息 id，生成方法待研究，需要会前端的帮帮忙
	"timestamp": "1718284699364000", // 时间戳
	"isMentionAll": false, // 是否 @ 了所有人
	"mentionList": [{
		"person": "", // 用户的 UID
		"isBot": false, // 是否为机器人
		"botType": "", // 机器人类型，估计未来会区分官方的和社区开发者的
		"offset": -1 // 偏移量？不知道有什么用
	}], // 提到的用户
	"styleTags": [], // 不知道有什么用
	"referenceMessageId": null, // 填写想要回复的消息的 id，此 id 不是 clientMessageId
	"animated": false, // 不知道
	"displayName": "", // 不知道
	"duration": 0, // 不知道
	"content": "hello  (met)b0facec027b411efb4225a6d6cf6ddec(met)  hello!" // 消息的内容，应该会以生文本显示，文本支持 markdown
}
```

响应：

```json
{
	"status": true,
	"data": {
		"messageId": "", // 消息的 ID，和参数中的 clientMessageId 不相同！
		"timestamp": "1718285266584264" // 时间戳
	},
	"message": null,
	"error": null,
	"code": "200"
}
```

