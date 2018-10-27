# TODO
> http://localhost/Xqn/Index/collect
这个接口有问题 有的地方用这个进行关注和取关 有的地方只用作关注 取关由ceilcollect实现。有一个属性 data-id 还没明确具体指代的是什么，如何生成的等也没搞懂。
# 1.chat

*http://localhost/Xqn/Msg/chatlist*
##### 描述
请求对话列表
##### 输入
```python
uid     // 我的用户识别码
cid     // 好友的用户识别码
```

##### 输出
```python
status // '200' means success
list: {
    uid         //该信息包的用户识别码
    createtime  //创建时间
    content     //内容
    pic         //图片的url
}
```
##### 报错
***

*http://localhost/Xqn/Msg/chat*
##### 描述
聊天发送消息
##### 输入
```python
uid // 我的用户识别码
cid // 好友的用户识别码
content // 发送的聊天内容
```

##### 输出
```python
status  //'200' means success
1.msg: { //两种形态 当返回'200'时为
    uid         //该信息包的用户识别码
    createtime  //创建时间
    content     //内容
    pic         //图片的url
}
2.msg // status不为'200'时的字符串错误信息
```
##### 报错
***

*http://localhost/Msg/upload*
##### 描述
上传图片
##### 输入
```python
files: {
    avatar  // 字符串 一张本地图片缩略图的路径
},
values: {
    uid     // 我的用户识别码
    cid     // 好友的用户识别码
}
```

##### 输出
```python
createtime  // 字符串 创建时间
url         // 字符串 图片链接
success     // 字符串 '1'表示成功 其他表示失败
```
##### 报错
***

# 2.details

*http://localhost/Xqn/Index/collect*
##### 描述
关注列表
##### 输入
```python
uid // 我的用户识别码
cid // 好友的用户识别码
```
##### 输出
```python
msg     // 字符串信息
status  // '200' means success
```
##### 报错
***

*http://localhost/Xqn/Index/zan*
##### 描述
为某一消息点赞并返回点赞数
##### 输入
```python
uid // 我的用户识别码 从本地cookie中提取
pid // 也是一个识别码 指代data-id
cid // 好友的用户识别码 指代data-cid
nickname // 我的用户昵称 从本地cookie中提取
```

##### 输出
```python
status // '200' means success
zan // html代码 替换的值 点赞的数量
msg // 字符串 '200'或其他均有提示 是否点赞成功
```
##### 报错
***

*http://localhost/Xqn/Publish/evaluate*
##### 描述
评论某条消息
##### 输入
```python
values: {
    content     // string 评论内容
    uid         // string
    pid         // string
    cid         // string
    nickname    // 本地cookie中的用户昵称
}
```

##### 输出
```python
status  // '200' means success
msg     // string 错误信息
```
##### 报错
***

# 3.editPwd

*http://localhost/Xqn/User/editpwd*
##### 描述
修改密码
##### 输入
```python
pwd // string 密码
id  // string 用户识别码
```

##### 输出
```python
status  // '200' means success
msg     // string 成功或错误信息
```
##### 报错
***

# 4.find

*http://localhost/Xqn/Index/findFirends*
##### 描述
根据通讯录寻找朋友
##### 输入
```python
一个二维数组stringfy后的JSON
JSON:[
    [
        fullName,   // string 用户全名
        phone       // string 用户的一个手机
    ], ...
]
```

##### 输出
```python
一个字典组成的数组JSON
[
    {
        avatar,     // 用户头像链接
        id,         // 用户id
        collect,    // 用于前端判断是否被我关注
        name,       // 用户名字
        nickname    // 用户昵称
    }, ...
]
```
##### 报错
***

*http://localhost/Xqn/Index/collect")}*
##### 描述
关注与取关操作
##### 输入
```python
uid     //
cid     //
```

##### 输出
```python
status  // '200' means 已关注成功; '300' means 已取消关注成功; 其他 means 操作失败
msg     // string 各种情况的提示信息
```
##### 报错
***

*{:U("xqn/Login/invite")}*(邀请操作，该操作被注释)
##### 描述
##### 输入
##### 输出
##### 报错
***

# 5.forget

*http://localhost/Login/sendCode*
##### 描述
向指定手机发送验证码
##### 输入
```python
mobile  // 电话号码
```

##### 输出
```python
status  // '200' means success
msg     // 
```
##### 报错
***

*http://localhost/Xqn/Login/forget*
##### 描述
忘记密码之后修改密码操作
##### 输入
```python
mobile  // string 用户手机号
pwd     // 新修改的密码
code    // 验证码
```

##### 输出
```python
status  // '200' means 修改成功
msg     // string 失败信息
```
##### 报错
***

# 6.friend_profile

*http://localhost/Xqn/Index/collect*
##### 描述
关注与取消操作 前已有定义
##### 输入
```python
uid
cid
```

##### 输出
```python
status
msg
```
##### 报错
***

*http://localhost/Xqn/Index/ceilCollect")}*
##### 描述
取消关注 （该操作似乎与collect操作重复）
##### 输入
```python
uid
cid
```

##### 输出
```python
status  // '200' means success
msg     // 错误提示信息
```
##### 报错
***

*http://localhost/Xqn/Upload/upload*
##### 描述
上传图片
##### 输入
```python
files:{
    avatar  // 图片路径
}
```

##### 输出
```python
success // '1' means success
msg     // 提示信息
id      // 未知用处
```
##### 报错
***

# 7.home

*http://localhost/Xqn/Index/collect*
##### 描述
关注
操作 之前已有定义
##### 输入
```python
uid
cid
```

##### 输出
```python
status
msg
```
##### 报错
***

*http://localhost/Xqn/Index/zan*
##### 描述
点赞操作 之前已有定义
##### 输入
```python
uid
pid
cid
nickname
```

##### 输出
```python
status
msg
zan
```
##### 报错
***

*http://localhost/Xqn/Publish/evaluate*
##### 描述
评论内容 之前已有定义
##### 输入
```python
values: {
    content :  content,
    uid :  $api.getStorage('userInfo').id,
    pid :  pid,
    cid: cid,
    nickname:nickname
}
```

##### 输出
```python
status
msg
```
##### 报错
***

# 8.index

*http://localhost/Xqn/Index/banner*
##### 描述
莫名其妙的操作 实现了一个页面跳转
##### 输入
```python
无
```
##### 输出
```python
无
```
##### 报错
***

# 9.login

*http://localhost/Xqn/Login/login*
##### 描述
登陆接口
##### 输入
```python
mobile  // 注册的手机号
pwd     // 密码
```
##### 输出
```python
status  // '200' means success
msg     // 成功或失败信息
```
##### 报错
***

# 10.my_collect

*http://localhost/Xqn/User/ceilCollect*
##### 描述
取关操作
##### 输入
```python
uid
cid
```
##### 输出
```python
status // '200' means success
msg
```
##### 报错
***

# 11.my_follower

*http://localhost/Xqn/Index/collect*
##### 描述
关注操作 之前有定义
##### 输入
```python
uid
cid
```

##### 输出
```python
status
msg
```
##### 报错
***

# 12.my_publish

*http://localhost/Xqn/Upload/upload*
##### 描述
上传文件 之前有定义
##### 输入
```python
files: {
    avatar: ret.data
}
```

##### 输出
```python
success
msg
id
```
##### 报错
***

*http://localhost/User/background*
##### 描述
更改背景图片图片中的一步
##### 输入
```python
values: {
    id          // 本地用户id
    background  // 调用Upload接口后返回包中的id值
}
```
##### 输出
```python
status  // '200' means success
msg     // 报错信息
```
##### 报错
***

# 13.personal

*http://localhost/Xqn/Register/prov*
##### 描述
根据城市、id、省份等返回用户列表
##### 输入
```python
id  // 可选值：'1', '2', '36, $userInfo.prov, $userInfo.city
```
##### 输出
```python
[
    [
        id,     // 用户id
        name    // 用户姓名
    ], ...
]
```
##### 报错
***

*http://localhost/Upload/upload*
##### 描述
上传文件 之前已有定义
##### 输入
```python
files: {
    avatar: ret.data
}
```

##### 输出
```python
success
id
```
##### 报错
***

*http://localhost/Xqn/User/personal*
##### 描述
注册接口
##### 输入
```python
values: {
    id          // uid 此处注意 这个不是用户自己填写的 请后端同学帮忙看看uid的生成机制
    avatar      // 上传文件后返回的id
    nickname    // string 昵称
    work        // string 工作单位
    profession  // string 原从事职业
    prov        // string 省份
    city        // string 城市
    dist        // string 县区
    address     // string 详细地址
    birthday    // string 出生日期
    sex         // string 性别
    education   // string 受教育程度
}
```
##### 输出
```python
status  // '200' means success
msg     // 成功或报错信息
data    // 数据包，用于存入cookie
```
##### 报错
***

# 14.post

*http://localhost/Upload/upload*
##### 描述
上传文件 之前已有定义
##### 输入
```python
files: {
    avatar: item.thumbPath
}
```

##### 输出
```python
success
id
url
```
##### 报错
***

*http://localhost/Publish/uploadVideo*
##### 描述
上传视频
##### 输入
```python
files: {
    avatar  // 文件路径
}
```

##### 输出
```python
success // '1' means success
url     // 视频链接
id      // 未知用处
```
##### 报错
***

*http://localhost/Publish/publish*
##### 描述
发表动态接口
##### 输入
```python
values: {
    content     // string 朋友圈内容
    uid         // string 用户id
    tid         // string 话题信息
    position    // string 定位信息
    pics        // string 上传照片的id并以','分隔
    video       // string 上海窜的视频id
}
```
##### 输出
```python
status  // '200'  means success
msg     // string 成功或报错信息
```
##### 报错
***

# 15.profile

*http://localhost/Xqn/Login/logout*
##### 描述
登出接口
##### 输入
无
##### 输出
```python
status  // '200' means success
msg     // 报错信息
```
##### 报错
***

# 16.publish_ajax_list

*http://localhost/Xqn/Publish/delete*
##### 描述
删除这条说说接口
##### 输入
```python
id  // 应当是这条说说的id
```
##### 输出
```python
status  // '200' means success
msg     // 成功或报错信息
```
##### 报错
***

# 17.register_more

*http://localhost/Xqn/Register/prov*
##### 描述
根据城市、id、省份等返回用户列表 之前已有定义
##### 输入
```python
id
```
##### 输出
```python
[
  {id: , name: }, ...
]
```
##### 报错
***

*http://localhost/Xqn/Upload/upload*
##### 描述
上传文件 之前已有定义
##### 输入
```python
files: {
    avatar: ret.data
}
```
##### 输出
```python
success
id
```
##### 报错
***

*http://localhost/Xqn/Register/register*
##### 描述
注册接口2 （不知道为什么搞了两个接口）
##### 输入
```python
values: {
    mobile      // 电话号码
    pwd         // 密码
    avatar      // 上传文件后返回的id
    nickname    // string 昵称
    work        // string 工作单位
    profession  // string 原从事职业
    prov        // string 省份
    city        // string 城市
    dist        // string 县区
    address     // string 详细地址
    birthday    // string 出生日期
    sex         // string 性别
    education   // string 受教育程度
}
```
##### 输出
```python
status  // '200' means success
mag     // 成功或报错信息
```
##### 报错
***

# 18.register

*http://localhost/Xqn/Register/isRegister*
##### 描述
判断是否已注册
##### 输入
```python
mobile  // 手机号
```
##### 输出
```python
status  // '200' means 该手机号已被注册
msg     // 报错信息
```
##### 报错
***

# 19.report

*http://localhost/Xqn/Publish/report*
##### 描述
举报某位用户
##### 输入
```python
values: {
    reason      // string 理由
    uid         // 本人用户id
    pid         // 被举报用户id
}
```
##### 输出
```python
status  // '200' means success
msg     // 成功或报错信息
```
##### 报错
***

# 20.search_list

*http://localhost/Xqn/Index/collect*
##### 描述
关注操作 之前有定义
##### 输入
```python
uid
cid
```
##### 输出
```python
status
msg 
```
##### 报错
***

# 21.search

*http://localhost/Xqn/Publish/search*
##### 描述
搜索某关键词
##### 输入
```python
keyword // string 关键词
```
##### 输出
```python
status  // '200' means success 
list    // type 未知 结果列表
msg     // 报错信息
```
##### 报错
***

# 22.suggest

*http://localhost/Xqn/User/suggest*
##### 描述
在线提建议
##### 输入
```python
content // 建议内容
tel     // 电话号码 
```
##### 输出
```python
status  // '200' means success
msg     // 成功或报错信息
```
##### 报错
***

# 23.system_msg

*http://localhost/Xqn/Msg/read")}*
##### 描述
给出一个信息id，返回状态，是其他操作的验证
##### 输入
```python
id  // 消息的识别码
```
##### 输出
```python
status  // '200' means success
msg     // 报错信息
```
##### 报错
***

*http://localhost/Xqn/Msg/review*
##### 描述

##### 输入
```python
eid     // 与Msg/read接口的id是一个字段 即消息的识别码
content // 回复的内容
uid     // 用户id
cid     // 目标用户id
```
##### 输出
```python
msg // 返回信息
```
##### 报错
***

# 24.system_notice

*http://localhost/Xqn/Msg/readSystem*
##### 描述
给定一个信息id，返回状态
##### 输入
```python
id  // 即消息的识别码
```
##### 输出
```python
status  // '200' means success
msg     // 报错信息
```
##### 报错
***
