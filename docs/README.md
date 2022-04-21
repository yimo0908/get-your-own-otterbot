# 写在前面 
[![QQGroup](https://img.shields.io/badge/QQ%20Group-660557003-brightgreen)](https://jq.qq.com/?_wv=1027&k=2ecQU6AV)            [![](https://img.shields.io/badge/OtterBot-Bluefissure-brightgreen)](https://github.com/Bluefissure/OtterBot)            [![system](https://img.shields.io/badge/system-Windows-brightgreen)](https://www.microsoft.com/zh-cn/software-download)

**此页面所有内容基于Windows系统。有任何问题请[进群](https://jq.qq.com/?_wv=1027&k=2ecQU6AV)询问大佬，感谢合作。**

**All things in this page are based on Windows. If you have any question, please [join the QQ group](https://jq.qq.com/?_wv=1027&k=2ecQU6AV) to seek advice. Thanks for your cooperation.**

本文旨在提供简单的领养引导，如果你您有服务器、维护知识且有自建獭窝的需求，可以参考下面的链接： 

[![Linux](https://img.shields.io/badge/Linux-Bluefissure-brightgreen)](https://github.com/Bluefissure/OtterBot/wiki/%E5%BC%80%E5%8F%91%E6%96%87%E6%A1%A3)  [![Docker](https://img.shields.io/badge/Docker-Bluefissure-brightgreen)](https://github.com/Bluefissure/OtterBot/wiki/OtterBot-Docker)  [![Docker](https://img.shields.io/badge/Docker-mengshouer-brightgreen)](https://hub.docker.com/r/mengshouer/otterbot)  [![Windows](https://img.shields.io/badge/Windows-sandtechnology-brightgreen)](https://github.com/sandtechnology/OtterBot/wiki/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE%28Windows%29)


---

# [OtterBot](https://github.com/Bluefissure/OtterBot) 

A QQ bot for Final Fantasy XIV (mostly served for CN server).

---

# 前期准备 

1. 一个QQ小号

2. 一台接入了互联网的Windows电脑

---

# 正式领养 
## Step 1：在獭窝中注册

选择一个獭窝（见下方快捷链接）。

[![Website](https://img.shields.io/website?label=%20%E4%B8%BB%20%E7%AA%9D%20&style=social&up_message=link&url=https%3A%2F%2Fxn--v9x.net%2F)](https://xn--v9x.net/)  [![Website](https://img.shields.io/website?label=%20%E7%AC%94%20%E7%AA%9D%20&style=social&up_message=link&url=https%3A%2F%2Fbot.pencilss.top%2F)](https://bot.pencilss.top/)   [![Website](https://img.shields.io/website?label=%E9%B8%A1%E7%AA%9D&style=social&up_message=link&url=https%3A%2F%2Ftata.guomie.club%2F)](https://tata.guomie.club/)   [![Website](https://img.shields.io/website?label=%E9%A3%8E%E7%AA%9D&style=social&up_message=link&url=https%3A%2F%2Fbotapi.dead-war.cn)](https://botapi.dead-war.cn)   [![Website](https://img.shields.io/website?label=%E9%B1%BC%E5%A1%98&style=social&up_message=link&url=https%3A%2F%2Ftatabot.bingyin.org%2F)](https://tatabot.bingyin.org/)   [![Website](https://img.shields.io/website?label=%E9%B8%9F%E7%AA%9D&style=social&up_message=link&url=https%3A%2F%2Ftata.cyanclay.xyz%2F)](https://tata.cyanclay.xyz/)

<details><summary>首次进入该獭窝需要注册，注册步骤如下：</summary>

1. 正常输入邮箱（QQ邮箱），密码，勾选用户协议，点击注册。  

2. 注册失败，并反馈獭獭认证码，把消息发送给对应注册的窝的活着的机器人。

3. 再次输入邮箱（QQ邮箱），密码，勾选用户协议，这次有獭獭认证码了，点击注册。
</details>

<details><summary>在领养/更新机器人中添加对应的参数如下：</summary>

- 昵称(长度>2)：机器人的名字，你可以叫他獭獭2号，或者自己起名字

- QQ账号：机器人QQ号

- 主人QQ：你自己的QQ号

- Access Token(长度>5)：自定义这个机器人连接时的认证码，可以任意但不得为空。后续会用到请务必记下。

- Tuling Token(选填)：是否采用自定义的图灵机器人token，如不使用请留空，将自动移交獭獭的聊天机器人。

</details>

填写完毕后点击添加机器人保存。

请注意，提交后修改要保证机器人QQ号和Token填写正确，如果遗忘了Token请进群联系窝主。

## Step 2：选择机器人框架

可根据自身情况并参考[此文章](./choice.md)选择适合自己的客户端

---

# 占卜 

- **[win only]** mcl/onebot-kotlin可自行加载**mirai_native**插件后，在[群](https://jq.qq.com/?_wv=1027&k=2ecQU6AV)文件获得占卜插件的dll和json文件，放入`.\date\MiraiNative\plugins`文件夹即可
- **[all os]** 所有方式可以反向ws连接[基于nonebot重构的占卜插件](https://github.com/LittleNightmare/onebot_Astrologian_FFXIV)。**请注意nonebot的版本，v1 v2互不兼容。**

---

# 注意事项 

!>1. 拉机器人进入新群，或退出旧群后。可能需要使用`/bot update`来刷新机器人的群缓存 。  
2. 必须保持框架打开状态，机器人才在工作

---

# License 
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fyimo0908%2Feasy-build-otterbot.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fyimo0908%2Feasy-build-otterbot?ref=badge_large)