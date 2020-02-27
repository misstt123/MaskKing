#


#### 介绍
中山市口罩预约平台脚本

平台网址：http://kz.yq.zszwfw.cn/kzyy-register/#/

#### 软件架构
软件架构说明
    使用firefox，加上运行脚本，开箱即用

#### 使用说明

# 3.0 油猴版
- 服务器上线了接口数据加密，签名。
- 排队机制修改页面重复点击会重置排队
- 前端页面增加了session，导致浏览器不能直接多开
- 前端页面增加了登录和抢购验证码。
- 前端页面js上避免了直接去掉button的disabled即可提交
- 前端页面加入了稳定的倒计时同步，切换tab即可立即同步时间，或定时同步时间

* postman或直接curl已无法提交，破解js的加密与签名工作量无法估计，直接放弃任何外部提交方法
* 使用firefox浏览器，并引入了浏览器插件Tampermonkey和Firefox Multi-Account Containers
* 油猴插件内加入js内容，循环检测倒计时结束时的按键状态，捕捉可以点击时立即点击，点击后立即停止
* Firefox Multi-Account Containers允许了firefox浏览器可以多个session账号登录，实现多开同时抢
* Tampermonkey: https://www.tampermonkey.net/
* Firefox Multi-Account Containers: https://github.com/mozilla/multi-account-containers#readme





# 2.0 SHELL版 & PY版
- 服务器上线了负载动态平衡，接口内路由跳转
- js直接提交失效，但postman或直接curl依然可以提交，因此

* 开发了shell版（py版友人开发），通过run.sh启动多个sh实现多号同时抢
* shell版使用curl方法提交，附加参数 -L: Follow redirects，-b: --cookie <data|filename> Send cookies from string/file，-H: --header <header/@file> Pass custom header(s) to server
* 获得结果json使用python解析，判断状态

但此版本2日就失效了





# 1.0 JS版
- 可以直接用JS循环提交，服务器接口无任何限制措施，通过多开浏览器实现多号并发抢

* 直接在html内加入phone和captcha，复制多个html添加相应号码，直接打开就可以

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 码云特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  码云官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解码云上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是码云最有价值开源项目，是码云综合评定出的优秀开源项目
5.  码云官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  码云封面人物是一档用来展示码云会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
