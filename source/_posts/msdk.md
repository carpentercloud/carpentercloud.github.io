---
title: 闪电玩微信小游戏sdk
date: 
tag: [sdk]
---

**简要描述：** 
提供两个js文件，文件名分为h5jssdk.js和mSdwH5.js,游戏把两个文件放在同一目录下，引入mSdwH5.js即可
<a href="http://www.shandw.com/libs/sdk/h5jssdk.js" download="h5jssdk.js">点击下载h5jssdk.js</a>
<a href="http://www.shandw.com/libs/sdk/mSdwH5.js" download="mSdwH5.js">点击下载mSdwH5.js</a>
<!--more-->
** 一、引入mSdwH5.js,并初始化 **
```
import Sdk from './mSdwH5.js'
var sdw = new Sdk({
  wxAppId:'wxd8b2bee01be573c1', // 小游戏appid
  channel: '10644', // 闪电玩分配的渠道id
  gid: '2005379277', // 闪电玩分配的游戏id
  gameVersion: "1.0.0"  // 游戏版本
})
```

**二、获取用户信息：** 
```
sdw.getAuthInfo({
  success: function(data){
    console.log(data);
  },
  fail: function(data){
    console.log("获取用户信息失败",data)
  }
})
```

**三、分享：** 
```
// 分享数据demo
var shareDataDemo = {
  title: "内置分享title",
  desc: "分享内容",
  imgUrl: "",
  success: function(res){
      console.log(res,"11");
  },
  fail: function(){
      console.log("share fail");
  }
}
// 小游戏自带的分享内容设置
sdw.onSetShareOperate(shareDataDemo);

// 游戏内自定义调用的分享
sdw.pltShare(shareDataDemo);
```

**四、用户协议及隐私政策配置指引：** 
```
// 腾讯游戏用户协议
sdw.openTencentGameContract();
// 隐私政策
sdw.openTencentPrivacyContract();
```
备注：上述两个接口需在微信基础库2.0.0以上版本支持，另外接口需真机调试

**五、退出：** 
```
// 参数非必填可以为空
sdw.pltExitMiniProgram({
  success:function(){
    console.log("exit");
  },
  fail: function(){}
})
```
  
**六、上报数据：**
- sdw.pltReport(type, reportData, objs) 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|type |是  |string |上报数据类型   |
|reportData |是  |obj | 上报数据    |
|obj     |否  |obj |    上报成功、失败回调 |

**type参数明细：** 

|参数名|上报数据类型|是否必选|说明|
|:----    |:---|:----- |-----   |
|SceneFlow |游戏资源位上报  |可选 |分析玩家在每个资源位的曝光点击情况   |
|GuideFlow |新手已到上报  |可选 | 分析玩家在新手引导的参与、通过、完成情况    |
|ActionFlow     |其它行为上报 |可选 |    玩家的其它行为数据，可以根据此接口上报，事件类型，游戏侧自己定义 |

**游戏资源位上报(SceneFlow)--reportData对象参数明细：** 

|参数名|数据类型|是否必选|说明|
|:----    |:---|:----- |-----   |
|vRoleID |string  |否 |角色id   |
|cardID |Number  | 是 | 页卡    |
|slotID     |number |是 |    槽位 |
|orderID     |number |是 |    次序 |
|iActionId     |number |是 |    行为类型 |
|extend     |obj |否 |    扩展字段，示例：：{"k1":"v1","k2":"v2",...} |


 **调用示例**

``` 
 sdw.pltReport('SceneFlow', 
  { vRoleID: "123", cardID: "34", slotID: "34", orderID: "324", iActionId: "34", extend: { key: 'value', key: 'value2' }},
  {
    success: function(data){
      console.log("上报成功:",data);
    },
    fail: function (e) {
      console.log("上报失败：", e);
    }
  });
```


