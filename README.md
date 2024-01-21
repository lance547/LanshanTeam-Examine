# LanshanTeam winter examine

###### 游戏逻辑不是我看重的，重心会放在性能上，使我的项目能够应对高并发场景

##### 基础功能：

* [X]  用户注册
* [ ]  用户登录
* [ ]  用户个人主页
* [ ]  添加游戏好友
* [ ]  大厅创建房间
* [ ]  大厅加入房间，多位玩家准备后开始游戏
* [ ]  基本游戏逻辑（任意选择一款游戏进行实现）：五子棋、象棋、坦克大战、贪吃蛇等等
* [ ]  积分排行榜/段位

##### 加分项：

* [ ]  用户密码加盐加密
* [ ]  用户登录有短信登录、邮箱登录、第三方登录多种形式
* [ ]  验证码（登录，注册，修改密码）
* [ ]  用户状态保存使用 JWT 或 Session
* [ ]  实现对局的断线重连
* [ ]  实现对局内聊天
* [ ]  实现好友邀请进行对局
* [ ]  实现观战功能
* [ ]  用户对局记录，要求能够复现每一步下法
* [ ]  将项目部署上线（包括前端和后端的项目，也就是登录你的网站能够像正常的网站一样访问）
* [ ]  使用 https 加密
* [ ]  合理的缓存策略（提高访问速度）
* [ ]  考虑服务端安全性（xxs，sql注入，cors，csrf 等）

1. [ ]  实现游戏性能的优化：容纳更多人同时在线、降低对局延迟等等，如果可以做测试进行优化前后对比就更好了

* [ ]  其他任何你想加的让我们耳目一新的功能...

### 架构

* [ ]

client-server

拆分成user，hall，game模块

#### User

用户注册:

1.电话号码，邮箱，github实名。这种方式实名才能进入进行排行榜排名,

2.游客注册，只使用密码注册

用户登陆

1.直接通过密码登陆

2.使用验证码登陆

3.OAuth2.0，github登陆

找回密码

用户信息

（包括积分，实名情况）（实名情况在数据库中：github实名：1分;邮箱实名：2分;电话号码实名：4分;）

补充用户信息

#### Hall

游戏大厅，从这里启动游戏

创建房间

加入房间，双方都准备后，房主启动游戏

邀请好友加入房间

观战

#### Game

游戏逻辑

游戏期间使用redis存储数据，游戏结束使用mysql存储

### 问题

1.当调用rpc服务时，出现error reading server preface: http2: frame too large

- 服务端换端口
