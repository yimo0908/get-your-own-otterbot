

# easy-build-otterbot

**本仓库所有内容基于windows系统。**

---

<p align="center">推荐使用</p>

---

## 1. mcl (mirai console loader)+onebot-mirai

配置方法：[Click me](./doc/mcl.md)

优点：持续更新，且可通过对应脚本指令下载更新本体与插件；可自行加载其他mirai插件，缝合想要的功能

缺点：需要安装`Java(TM) SE Development Kit 11`；因框架限制，无法使用`/help`指令

## 2. cqhttp-go

配置方法：[Click me](./doc/go.md)

优点：持续更新，不需要下载安装其他依赖

缺点：无法自动更新（有更新提示）

## 3. onebot-kotlin

配置方法：[Click me](./doc/onebot-kotlin.md)

优点：持续更新，可自行加载其他mirai插件，缝合想要的功能

缺点：需要安装`jre (Java SE Runtime Environment 8)`或`Java SE Development Kit 11.0.9`或`Java SE Development Kit 15`

## 4. OICQ

配置方法：[Click me](./doc/OICQ.md)

优点：持续更新~~且更新方便（至少个人觉得不是太方便）~~

缺点：需要安装`node.js`



---

<p align="center">开发中</p>

---



## 先驱+onebot-yaya

配置方法：[Click me](./doc/xq.md)

优点：框架有gui；可自行加载其他先驱插件，缝合想要的功能

缺点：开发中，目前只支持反向ws的部分功能orz



---

<p align="center">outdated</p>

---

## miraiOK+cqhttp-mirai

配置方法：[Click me](./doc/miraiOK.md)

优点：可自行加载其他mirai插件，缝合想要的功能

缺点：miraiOK已经停更，cqhttp-mirai也只能使用魔改版；因框架限制，无法使用`/help`指令



## 理论上都可缝合nonebot/HoshinoBot进行功能增加

