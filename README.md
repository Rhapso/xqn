#  1.chat

*http://localhost/Msg/chatlist*
### 必选输入：
uid: uid
cid: cid
### 可选输入：
### 输出：
list
### 错误信息：

*http://localhost/Msg/chat*
### 必选输入：
uid
cid
content
### 可选输入：
### 输出：
msg
### 错误信息：

http://localhost/Msg/upload
### 必选输入：
files: {
    avatar: item.thumbPath
},
values: {
    uid: uid,
    cid: cid
}
### 可选输入：
### 输出：
createtime
url
success
### 错误信息：

# 2.details

*{:U("xqn/Index/collect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
msg
status
### 错误信息：

*{:U("xqn/Index/zan")}*
### 必选输入：
uid
pid
cid
nickname
### 可选输入：
### 输出：
status
zan
msg
### 错误信息：

*http://localhost/Publish/evaluate*
### 必选输入：
values: {
    content :  content,
    uid :  $api.getStorage('userInfo').id,
    pid :  pid,
    cid :  cid,
    nickname: nickname
}
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 3.editPwd

*http://localhost/User/editpwd*
### 必选输入：
pwd
id
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 4.find

*{:U('Xqn/Index/findFirends')}*
### 必选输入：
一个二维数组stringfy后的JSON
JSON:[
  [fullName, phone], [fullName, phone], ...
]
### 可选输入：
### 输出：
一个字典组成的数组JSON
[
  {avatar: , id: , collect: , name: , nickname:}, ...
]
### 错误信息：

*{:U("xqn/Index/collect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

*{:U("xqn/Login/invite")}*(邀请操作，该操作被注释)
### 必选输入：
### 可选输入：
### 输出：
### 错误信息：

# 5.forget

*http://localhost/Login/sendCode*
### 必选输入：
mobile
### 可选输入：
### 输出：
status
msg
### 错误信息：

*http://localhost/Login/forget*
### 必选输入：
mobile
pwd
code
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 6.friend_profile

*{:U("xqn/Index/collect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

*{:U("xqn/Index/ceilCollect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

*http://localhost/Upload/upload*
### 必选输入：
files:{avatar: ret.data}
### 可选输入：
### 输出：
success
id
msg
### 错误信息：

# 7.home

*{:U("xqn/Index/collect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

*{:U("xqn/Index/zan")}*
### 必选输入：
uid
pid
cid
nickname
### 可选输入：
### 输出：
status
msg
zan
### 错误信息：

*http://localhost/Publish/evaluate*
### 必选输入：
values: {
    content :  content,
    uid :  $api.getStorage('userInfo').id,
    pid :  pid,
    cid: cid,
    nickname:nickname
}
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 8.index

*http://localhost/Index/banner*
### 必选输入：
### 可选输入：
### 输出：
### 错误信息：

# 9.login

*http://localhost/Login/login*
### 必选输入：
mobile
pwd
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 10.my_collect

*{:U("xqn/User/ceilCollect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 11.my_follower

*{:U("xqn/Index/collect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 12.my_publish

*http://localhost/Upload/upload*
### 必选输入：
files: {
    avatar: ret.data
}
### 可选输入：
### 输出：
success
msg
### 错误信息：

*http://localhost/User/background*
### 必选输入：
values: {
    id : $api.getStorage('userInfo').id,
    background : data.id
}
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 13.personal

*http://localhost/Register/prov*
### 必选输入：
id
### 可选输入：
### 输出：
[
  [id: , name: ], ...
]
### 错误信息：

*http://localhost/Upload/upload*
### 必选输入：
files: {
    avatar: ret.data
}
### 可选输入：
### 输出：
success
id
### 错误信息：

*http://localhost/User/personal*
### 必选输入：
values: {
    id: uid,
    avatar: avatar,
    nickname : nickname,
    work : work,
    profession : profession,
    prov : prov,
    city : city,
    dist : dist,
    address : address,
    birthday : birthday,
    sex : sex,
    education : education
}
### 可选输入：
### 输出：
status
msg
data
### 错误信息：

# 14.post

*http://localhost/Upload/upload*
### 必选输入：
files: {
    avatar: item.thumbPath
}
### 可选输入：
### 输出：
success
id
url
### 错误信息：

*http://localhost/Publish/uploadVideo*
### 必选输入：
files: {
    avatar: ret.data
}
### 可选输入：
### 输出：
success
url
id
### 错误信息：

*http://localhost/Publish/publish*
### 必选输入：
values: {
    content :  content,
    uid :  $api.getStorage('userInfo').id,
    tid :  tid,
    position :  position,
    pics : pics,
    video : video,
}
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 15.profile

*http://localhost/Login/logout*
### 必选输入：
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 16.publish_ajax_list

*http://localhost/Publish/delete*
### 必选输入：
id
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 17.register_more

*http://localhost/Register/prov*
### 必选输入：
id
### 可选输入：
### 输出：
[
  {id: , name: }, ...
]
### 错误信息：

*http://localhost/Upload/upload*
### 必选输入：
files: {
    avatar: ret.data
}
### 可选输入：
### 输出：
success
id
### 错误信息：

*http://localhost/Register/register*
### 必选输入：
values: {
    mobile :  mobile,
    pwd :  pwd,
    avatar :  avatar,
    nickname : nickname,
    work : work,
    profession : profession,
    prov : prov,
    city : city,
    dist : dist,
    address : address,
    birthday : birthday,
    sex : sex,
    education : education
}
### 可选输入：
### 输出：
status
mag
### 错误信息：

# 18.register

*http://localhost/Register/isRegister*
### 必选输入：
mobile
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 19.report

*http://localhost/Publish/report*
### 必选输入：
values: {
    reason :  content,
    uid :  $api.getStorage('userInfo').id,
    pid :  pid,
}
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 20.search_list

*{:U("xqn/Index/collect")}*
### 必选输入：
uid
cid
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 21.search

*http://localhost/Publish/search*
### 必选输入：
keyword
### 可选输入：
### 输出：
status
list
msg
### 错误信息：

# 22.suggest

*http://localhost/User/suggest*
### 必选输入：
content
tel
### 可选输入：
### 输出：
status
msg
### 错误信息：

# 23.system_msg

*{:U("xqn/Msg/read")}*
### 必选输入：
id
### 可选输入：
### 输出：
status
msg
### 错误信息：

*{:U("xqn/Msg/review")}*
### 必选输入：
eid
content
uid
cid
### 可选输入：
### 输出：
msg
### 错误信息：

# 24.system_notice

*{:U("xqn/Msg/readSystem")}*
### 必选输入：
id
### 可选输入：
### 输出：
status
msg
### 错误信息：
