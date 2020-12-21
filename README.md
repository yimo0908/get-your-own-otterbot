[![easy-build-otterbot](https://socialify.git.ci/yimo0908/easy-build-otterbot/image?description=1&logo=https%3A%2F%2Fraw.githubusercontent.com%2Fyimo0908%2Feasy-build-otterbot%2Fmain%2Fotter.jpg&owner=1&theme=Light)](https://github.com/Bluefissure/OtterBot/wiki/%E9%A2%86%E5%85%BB%E6%96%87%E6%A1%A3)

[![QQGroup](https://img.shields.io/badge/QQ%20Group-660557003-brightgreen)](https://jq.qq.com/?_wv=1027&k=2ecQU6AV)            [![](https://img.shields.io/badge/OtterBot-Bluefissure-brightgreen)](https://github.com/Bluefissure/OtterBot)            [![system](https://img.shields.io/badge/system-Windows-brightgreen)](https://next.itellyou.cn/Original/Index)

[![Website](https://img.shields.io/website?label=%20%E4%B8%BB%20%E7%AA%9D%20&style=social&up_message=link&url=https%3A%2F%2Fxn--v9x.net%2F)](https://xn--v9x.net/)  [![Website](https://img.shields.io/website?label=%20%E7%AC%94%20%E7%AA%9D%20&style=social&up_message=link&url=https%3A%2F%2Fbot.pencilss.top%2F)](https://bot.pencilss.top/) [![Website](https://img.shields.io/website?label=%20%E9%A3%8E%20%E7%AA%9D%20&style=social&up_message=link&url=https%3A%2F%2Fbotapi.dead-war.cn%2F)](https://botapi.dead-war.cn/) [![Website](https://img.shields.io/website?label=%E5%A1%94%E5%A1%94%E9%9C%B2%20&style=social&up_message=link&url=http%3A%2F%2Ftataru.aoba.vip%2Fmain.php)](http://tataru.aoba.vip/main.php)

**本仓库所有内容基于Windows系统。有任何问题请[进群](https://jq.qq.com/?_wv=1027&k=2ecQU6AV)询问大佬，感谢合作。**

**All things in this repository are based on Windows. If you have any question, please [join the QQ group](https://jq.qq.com/?_wv=1027&k=2ecQU6AV) to seek advice. Thanks for your cooperation.**

---

## OtterBot

A QQ bot for Final Fantasy XIV (mostly served for CN server).

And this repository aims to provide you the ways to build your otterbot.

---

## 前期准备

1. 一个QQ小号

2. 一台接入了互联网的Windows电脑

## 正式领养

#### Step 1：在獭窝中注册

登陆獭窝（见上方快捷链接）。

<details><summary>在领养/更新机器人中添加对应的参数如下：</summary>

- 昵称(长度>2)：机器人的名字，你可以叫他獭獭2号，或者自己起名字

- QQ账号：机器人QQ号

- 主人QQ：你自己的QQ号

- Access Token(长度>5)：自定义这个机器人连接时的认证码，可以任意但不得为空。后续会用到请务必记下。

- Tuling Token：是否采用自定义的图灵机器人token，如不使用请留空，将自动移交獭獭的聊天机器人。

</details>

填写完毕后点击添加机器人保存。

请注意，提交后修改要保证机器人QQ号和Token填写正确，如果遗忘了Token请进群联系群主。

#### Step 2：选择机器人框架

可根据自身情况并参考[此文章](./doc/README.md)选择适合自己的客户端

---

## 拓展

OtterBot通过反向ws与机器人框架的插件进行交流。而通常包含反向ws的插件同时具备正向ws、反向ws、http等功能，因此可以拓展

- [nonebot](https://docs.nonebot.dev/)/[HoshinoBot](https://github.com/Ice-Cirno/HoshinoBot)  - 反向ws
- [GroupManager](https://github.com/Yiwen-Chan/GroupManager) - 正向ws
- [塔塔露](http://tataru.aoba.vip/main.php) - post_url (http)
- 以及其他通过此3中方式连接的拓展

---

## 注意事项

> 1. 拉机器人进入新群，或退出旧群后。可能需要使用`/bot update`来刷新机器人的群缓存
> 2. 必须保持框架打开状态，机器人才在工作

