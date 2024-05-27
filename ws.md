Websocket 链接：wss://ws.oopz.cn/

## 连接后第一个发的包，同时也用作 Ping 包
```json
{
	"time": "", // 当前时间戳
	"body": "{\"person\":\"\",\"deviceId\":\"\",\"signature\":\"\",\"deviceName\":\"\"}",
	"event": 253 // 事件 ID
}
```
它的 body 是一个纯文本，但是这个文本是一个 json 文本，将其格式化一下
```json
{
    "person": "", // UID
    "deviceId": "", // 设备 ID
    "signature": "", // 登录后获得的 ID
    "deviceName": "" // 值和设备 ID 一致
}
```

## 发完第一个包后回复的包
```json
{
	"time": "1716827971438",
	"event": 1,
	"body": "{\"serverId\":\"\"}"
}
```
body 内容：
```json
{
    "serverId": "" // 服务器 ID，不知道有什么用，可能是每个用户连接服务器都是延迟最低的吧？
}
```

## 消息事件
```json
{
	"time": "1716828026216",
	"event": 9,
	"body": "{\"type\":\"TEXT\",\"data\":\"{\\\"target\\\":\\\"\\\",\\\"area\\\":\\\"01H9HEP21E7B0PXD1DHN6WQP43\\\",\\\"channel\\\":\\\"01H9QP0AJ443JY6FA0TN6Y619J\\\",\\\"type\\\":\\\"TEXT\\\",\\\"clientMessageId\\\":\\\"V9es5jBS2VrNRGhVzfYAL\\\",\\\"messageId\\\":\\\"42572565083848705\\\",\\\"timestamp\\\":\\\"1716828026199390\\\",\\\"person\\\":\\\"d57e5097191111ef9f870213468d1701\\\",\\\"content\\\":\\\".....................GTAOL..............................~\\\\n.............................................GTAOL...............~https://oopz.cn/i/YDHh34\\\",\\\"mentionList\\\":[],\\\"isMentionAll\\\":false,\\\"senderIsBot\\\":false,\\\"senderBotType\\\":\\\"\\\",\\\"styleTags\\\":[],\\\"referenceMessageId\\\":null}\"}"
}
```
body 内容：
```json
{
	"type": "TEXT", // 消息类型
	"data": "{\"target\":\"\",\"area\":\"01H9HEP21E7B0PXD1DHN6WQP43\",\"channel\":\"01H9QP0AJ443JY6FA0TN6Y619J\",\"type\":\"TEXT\",\"clientMessageId\":\"V9es5jBS2VrNRGhVzfYAL\",\"messageId\":\"42572565083848705\",\"timestamp\":\"1716828026199390\",\"person\":\"d57e5097191111ef9f870213468d1701\",\"content\":\".....................GTAOL..............................~\\n.............................................GTAOL...............~https://oopz.cn/i/YDHh34\",\"mentionList\":[],\"isMentionAll\":false,\"senderIsBot\":false,\"senderBotType\":\"\",\"styleTags\":[],\"referenceMessageId\":null}" // 数据
}
```
data 内容：
```json
{
	"target": "",
	"area": "01H9HEP21E7B0PXD1DHN6WQP43", // 域，就是 discord 的服务器，qq 的群
	"channel": "01H9QP0AJ443JY6FA0TN6Y619J", // 发送消息的子频道
	"type": "TEXT", // 消息类型
	"clientMessageId": "V9es5jBS2VrNRGhVzfYAL", // 客户端消息的 ID
	"messageId": "42572565083848705", // 消息的 ID
	"timestamp": "1716828026199390", // 发送时间戳
	"person": "d57e5097191111ef9f870213468d1701", // 发送的用户的 ID
	"content": ".....................GTAOL..............................~\n.............................................GTAOL...............~https://oopz.cn/i/YDHh34", // 发送的文本的内容，markdown 格式
	"mentionList": [], // @ 的用户列表
	"isMentionAll": false, // 是否 @ 全体成员
	"senderIsBot": false, // 发送者是否为机器人
	"senderBotType": "", // 如果发送者是机器人，这个机器人是什么类型的机器人
	"styleTags": [], // 不知道有什么用
	"referenceMessageId": null // 应该是回复的消息的 ID
}
```