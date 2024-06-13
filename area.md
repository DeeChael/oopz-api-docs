## 获取用户加入的域
GET: https://api.oopz.cn/userSubscribeArea/v1/list
响应：
```json5
{
    "status": true,
    "data": [
        {
            "id": "01H9HEP21E7B0PXD1DHN6WQP43", // 域 ID
            "code": "979129", // 和 KOOK 类似的 Public ID 可能是，我猜的
            "name": "Oopz活动/问题反馈", // 域的名称
            "avatar": "https://areacdn.oopz.cn/area/avatar/home_page/guanfang.webp?sign=1716827974-N9rseA-0-cecace70de3b3888ae66af22a4443ebd", // 域图标
            "banner": "https://areacdn.oopz.cn/area/banner/home_page/banner_guanfang.webp?sign=1716827974-5XPmYP-0-75710e28a6f16b9ebc22f81cf8d8f754", // 域头图
            "level": 0, // 你在这个域里面的等级
            "owner": "638a880a6d7811eea2fb0ee79096402c" // 域主的 UID
        },
        ...
    ],
    "message": null,
    "error": null,
    "code": "200"
}
## 获取用户加入的域，我不知道为什么数据差不多为什么要用两个 URL
GET: https://api.oopz.cn/client/v1/area/v1/home/v1/subscribed
响应：
```json5
{
    "status": true,
    "data": [
        {
            "id": "01H9HEP21E7B0PXD1DHN6WQP43",
            "code": "979129",
            "name": "Oopz活动/问题反馈",
            "avatar": "https://areacdn.oopz.cn/area/avatar/home_page/guanfang.webp?sign=1716827974-tWc5WE-0-435df25fa3af722b1da1d139a37c45ba",
            "banner": "https://areacdn.oopz.cn/area/banner/home_page/banner_guanfang.webp?sign=1716827974-9P8ltE-0-f08ebfa57ddc616bc08d4a0958473cb5",
            "number": 780, // 不知道是干什么的
            "top": false, // 置顶？但我没在客户都安找到相关功能
            "createTime": "1715927530151", // 创建时间
            "level": 1,
            "owner": "638a880a6d7811eea2fb0ee79096402c"
        },
        ...
    ],
    "message": null,
    "error": null,
    "code": "200"
}
```
```
## 获取官方推荐的头图域
GET: https://api.oopz.cn/v1/discovery/banner
响应：
```json5
{
    "status": true,
    "data": [
        {
            "area": "01H9HF08JZV1151QVCXNH147YA",
            "name": "Apex英雄",
            "banner": "",
            "carousel": "https://areacdn.oopz.cn/area/banner/20240227/143f4b6ed51f11ee84c886e6e448129521312312.webp?sign=1716827957-UHnP3K-0-2751a3c0f175715a3f9dd3a09e7a455e", // 头图专用的图片
            "livingPersonNum": 1854230, // 用户人数
            "code": "769171",
            "desc": "传奇们，欢迎来到《Apex Legends》！捍卫者是你吗？", // 简介
            "avatar": "https://areacdn.oopz.cn/area/avatar/home_page/apex_hero.webp?sign=1716827957-Rs26Yg-0-da6626b7853106f39458bc31d3e14bdd"
        },
        ...
    ],
    "message": null,
    "error": null,
    "code": "200"
}
```
## 获取主页推荐的域
GET: https://api.oopz.cn/v1/discovery/recommend
参数：
```json5
{
    "size": 100, // 获取的域数量，但实际上官方的推荐远远到不了这个数量，这个数只是为了尽量获得全所有的域
    "page": 1 // 获取的是第几页
}
```
响应：
```json5
{
    "status": true,
    "data": [
        {
            // 参考官方推荐的头图域
            "area": "01H9HEP21E7B0PXD1DHN6WQP43",
            "name": "Oopz活动/问题反馈",
            "banner": "https://areacdn.oopz.cn/area/banner/home_page/banner_guanfang.webp?sign=1716827974-2P9GHm-0-5cde01f66eeb167b1bbc0a8d2b77fd8d",
            "carousel": "",
            "livingPersonNum": 1526362,
            "code": "979129",
            "desc": "Oopz官方域，欢迎来此反馈问题和建议，还有很多有趣的活动等你哦！",
            "avatar": "https://areacdn.oopz.cn/area/avatar/home_page/guanfang.webp?sign=1716827974-QHrro5-0-0faaa27124233ae7af5a888b0e433252"
        },
        ...
    ],
    "message": null,
    "error": null,
    "code": "200"
}
```
## 获取域的信息
GET: https://api.oopz.cn/client/v1/area/v1/detail/v1/info
参数：
```json5
{
    "area": "" // 域的 ID
}
```
响应：
```json5
{
    "status": true,
    "data": {
        "id": "01HWSJMG64B4DRZC3S3090XQAH", 
        "code": "358666626", // 不知道
        "name": "D6", // 域的名称
        "banner": "https://areacdn.oopz.cn/default/area_default_background_v3.webp?sign=1716827974-uYCivC-0-d92b6c170de312379d9d1111cbc31ae4",
        "avatar": "https://areacdn.oopz.cn/default/area_default_avatar4_v4.webp?sign=1716827974-D03Kjc-0-0e16aa0ea34be3429076db03ec9633c1",
        "role": "b623dba0079011efa12c0aacbd5b115a", // 角色，但不知道为什么域有这个，好像是获取这个信息的人在这个域的角色
        "level": 16,
        "subscribed": true, // 是否已订阅，就是加入
        "privilegeKeys": [
            "MANAGE_ROLE_MEMBER",
            "MOVE_VOICE",
            "BLOCK_MEMBER",
            "DISABLE_TEXT",
            "DISABLE_VOICE",
            "MOVE_MEMBER",
            "MANAGE_GROUP",
            "MANAGE_CHANNEL",
            "MENTION_ALL",
            "TOP_MESSAGE",
            "RECALL_MESSAGE",
            "IMPORTANT_MESSAGE",
            "ORGANIZE_LOTTERY"
        ], // 我不知道是什么
        "privateChannels": [], // 私有频道
        "editCount": 1, // 编辑次数？
        "disableTextTo": null, 
        "disableVoiceTo": null,
        "isPublic": false, // 是否公开，公开的可以被搜到
        "areaRoles": [
            {
                "role": "b623dba0079011efa12c0aacbd5b115a", // 角色 ID
                "name": "域主", // 角色名称
                "level": 16 // 角色等级，高等级的角色会优先显示
            },
            ...
        ]
    },
    "message": null,
    "error": null,
    "code": "200"
}
```

## 获取域模板

GET：https://api.oopz.cn/v1/area/getAreaModel

无参数

响应：

```json
{
    "status": true,
    "data": [ // 因为这边数据我觉得很好懂所以就不写注释了，毕竟我不是官方 doc，没必要面面俱到
        {
            "id": "01GY6MPEG5PDM92MN0Q1QCHPMI",
            "name": "自己创建",
            "desc": "独立完善或邀请好友共同创建特色频道",
            "recommendTips": ""
        },
        {
            "id": "01GY6MPEG4697PBDE5X8K14XNE",
            "name": "深度玩家",
            "desc": "语音与文字频道并行满足游戏社交需求",
            "recommendTips": ""
        },
        {
            "id": "01GX2TMKC1WGF5188EVDFQBBYJ",
            "name": "游戏玩家",
            "desc": "拥有多个语音频道便于即时交流",
            "recommendTips": ""
        },
        {
            "id": "01GY6MPEG5PDM92MN0PY5X44ZJ",
            "name": "公会玩家",
            "desc": "已搭建不同频道模板用于公会运营",
            "recommendTips": ""
        }
    ],
    "message": null,
    "error": null,
    "code": "200"
}
```

## 创建域

POST：https://api.oopz.cn/v1/area/createAreaByModel

参数：

```json
{
	"name": "", // 名称
	"modelId": "" // 模板的 id，非必要建议直接使用 01GY6MPEG5PDM92MN0Q1QCHPMI 最为方便
}
```

响应：

```json
{
    "status": true,
    "data": {
        "area": "" // 创建好的域的 ID
    },
    "message": null,
    "error": null,
    "code": "200"
}
```

## 修改域的头像

PUT：https://api.oopz.cn/client/v1/area/v1/avatar

参数：

```json
{
	"area": "", // 域的 id
	"path": "/area/avatar/20240613/8744ecd1298911efb78f92af0254bb47.webp", // 路径，估计必须使用官方的图床，但我没找到上传接口
	"edit": false // 如果是修改应该要填 true，我这个响应是在创建域扒的
}
```

响应：

```json
{
	"status": true,
	"data": true, // 是否成功
	"message": null,
	"error": null,
	"code": "200"
}
```

