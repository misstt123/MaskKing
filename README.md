#

#### 介绍
2020抗击新冠状病毒中山市口罩预约平台脚本

平台网址：http://kz.yq.zszwfw.cn/kzyy-register/#/

#### 软件架构
软件架构说明
    使用firefox，加上运行脚本，开箱即用
     - v3.0版本:火狐脚本
      - v2.0
#### 使用说明

# 4.0 机器学习版（测试中，预计两天上传！）
- 使用cookie，但不能多开
- 增加机器学习识别验证码
- 需要额外添加远程服务器

- 验证码识别项目:https://github.com/cycz/EasyCaptcha

# 3.0 油猴版
- 口罩预约服务器进行了改造防抢，成功率并不是百分百
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


