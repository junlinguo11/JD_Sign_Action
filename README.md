# 基于 github action 的京东自动化签到

测试

## 介绍

> 使用 NobyDa “京东多合一签到脚本”为基础，移植到 github actions 自动化执行。

## 触发方式

- 点亮`Star`
- 凌晨 4 点定时执行
- 自定义：.github/workflows/work.yaml 编辑

## 注意问题

> **问题一：[项目 Fork 后定时任务没有执行](https://github.com/ZHDeveloper/JD_Sign_Action/issues/3)**
>
> > 1、建议修改 README.md 提交，以触发定时任务。
> >
> > 2、定时任务的时间是 UTC 时间，跟中国时间有 8 小时的时差。
>
> **问题二：京东 Cookie 的有效期**
>
> > 就我自己项目中的使用情况而言，一个月有效期。

## 使用用法

- 点击右上角 `Fork` 项目；
- `Settings` -> `Secrets` 中添加京东 Cookie、Server 酱 SCKEY；
  - `JD_COOKIE`：账号 1Cookie
  - `JD_DUAL_COOKIE`：账号 2Cookie(选填)
  - `PUSH_KEY`：Server 酱 SCKEY
- 点击`Star`，任务会自动执行，运行进度和结果可以在`Actions`页面查看；
- 当任务运行完成时，会将运行结果和错误信息打包到`Artifacts`，可自行下载查看；
- 如果配置了 Server 酱，运行结果会推送到微信；

## 获取京东 cookie

- 使用项目中的 Chrome 插件：`JDCookie`；
- Chrome 中拓展程序开启`开发者模式`；
- 点击`加载已解压的拓展程序`，选择`JDCookie`目录；
- 登录[领京豆](https://bean.m.jd.com/)；
- 点击`JDCookie`即可拷贝京东 cookie；

## 获取 Server 酱 SCKEY

- github 授权登录[Server 酱](http://sc.ftqq.com/3.version)官网；
- 菜单栏`微信推送`扫描绑定微信；
- 菜单栏`发送消息`拷贝 SCKEY；

## 效果截图

![WechatIMG3](./images/WechatIMG3.jpeg)

![WechatIMG4](./images/WechatIMG4.jpeg)

## 参考项目

- [NobyDa/Script/JD-DailyBonus](https://github.com/NobyDa/Script/blob/master/JD-DailyBonus/JD_DailyBonus.js)
- [ruicky/jd-sign-bot](https://github.com/ruicky/jd_sign_bot)
- [jerrykuku/luci-app-jd-dailybonus](https://github.com/jerrykuku/luci-app-jd-dailybonus)
