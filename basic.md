Headers 需要的数据（签名是必须的，其他的我不确定）：  
Oopz-Signature：在登录步骤获取的签名  
Oopz-Sign：和上方一致  
Oopz-App-Version：Oopz 的版本，比如 0.15.59  
Oopz-App-Version-Number：Oopz 的纯数字版本 15059，推测应该是将上方那个版本号应该看作 X.YY.ZZZ，因为 X 为 0 所以前面没有数字；而 YY 为 15 所以为 15；因为 ZZZ 有三位所以在后面添加 059。最终结果为 15059  
Oopz-Device-Id：设备 ID，不知道生成方法  
Oopz-Person：用户的 UID  
Oopz-Time：应该是当前时间戳

## 响应的基本格式
```json5
{
    "status": true, // 状态，不知道有什么用
    "data": 对应 API 所获取到的内容,
    "message": null, // 响应文本
    "error": null, // 报错讯息
    "code": "200" // 200 代表响应成功，其他数字代表失败
}
```
