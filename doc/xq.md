# 先驱獭

1) 下载[先驱框架（测试版）](http://api.xianqubot.com/index.php?newver=beta)与[OneBot-YaYa](https://github.com/Yiwen-Chan/OneBot-YaYa/releases) 并解压

2) 解压先驱框架到文件夹，并运行[先驱.exe](http://api.xianqubot.com/index.php?newver=beta)，待相关文件生成完毕后，将`OneBot-YaYa.XQ.dll`放入`.\Plugin`，重启先驱框架

3) 切到`账号管理`界面登录机器人账号

4) 从獭窝下载配置文件并替换`.\OneBot\config.yml`（客户端选择YaYa）

<details><summary>或根据实际情况编辑`.\OneBot\config.yml`文件</summary>

- [獭獭](https://xn--v9x.net/)
1. `master`改为`自己的QQ号`
2. `bots` --> `bot`改为在獭獭后台申请的`姬气人QQ`
3. `bots` --> `websocket_reverse` --> `name` 改为`獭獭`
4. `bots` --> `websocket_reverse` --> `enable` 改为`true`
5. `bots` --> `websocket_reverse` --> `url` 改为獭獭后台申请姬气人窝所在的`网址`,有下面四种情况：
```
主窝 ws://xn--v9x.net:80/ws
笔窝 ws://bot.pencilss.top/ws
风窝 ws://temp.dead-war.cn/ws
鸡窝 ws://tata.guomie.club/ws
```
6. `bots` --> `websocket_reverse` --> `access_token` 改为獭獭后台申请时所填的`token`

- [塔塔露](http://tataru.aoba.vip/cloud/)
1. `master`改为`自己的QQ号`

2. `bots` --> `bot`改为在獭獭后台申请的`姬气人QQ`

3. `bots` --> `http` --> `name` 改为`塔塔露`

4. `bots` --> `http` --> `enable` 改为`true`

5. `bots` --> `http` --> `post_url` 改为塔塔露后台右上角个人信息里的API的`网址`

</details>


<details><summary>5. 详细的配置文件说明</summary>

```
# 版本
version: 1.0.5
# 主人QQ号
master: 12345678
# 是否开启DEBUG日志
debug: true
# 心跳设置，默认不动
heratbeat:
  enable: true
  interval: 10000
# 缓存设置，暂未实现
cache:
  database: false
  image: false
  record: false
  video: false
# 不同姬气人的设置，注意yaml中 "-" 代表一个父节点有多个子节点
bots:
# 被设置的姬气人QQ
- bot: 0
  # 正向WS
  websocket:
  # 连接到的服务的名字，自己起
  - name: WSS EXAMPLE
    # 是否启动该服务的连接，连接为 true
    enable: false
    # OneBot建立服务器的HOST，无特殊需求一般为 127.0.0.1
    host: 127.0.0.1
    # OneBot建立服务器的PORT，与插件的端口要对应
    port: 6700
    # OneBot服务器 Token ,一般不动
    access_token: ""
    # OneBot上报格式，可为 string 或 array ，一般不动
    post_message_format: string
  # 反向WS
  websocket_reverse:
  # 连接到的服务的名字，自己起
  - name: WSC EXAMPLE
    # 是否启动该服务的连接，连接为 true
    enable: false
    # 插件服务器的地址，一般只需要改端口
    url: ws://127.0.0.1:8080/ws
    # 暂未实现
    api_url: ws://127.0.0.1:8080/api
    # 暂未实现
    event_url: ws://127.0.0.1:8080/event
    # 暂未实现
    use_universal_client: true
    # 插件填了 Token 这里也要填
    access_token: ""
    # OneBot上报格式，可为 string 或 array ，一般不动
    post_message_format: string
    # 掉线重连的时间间隔，单位毫秒
    reconnect_interval: 3000
  # HTTP 和 HTTP POST
  http:
  # 连接到的服务的名字，自己起
  - name: HTTP EXAMPLE
    # 是否启动该服务的连接，连接为 true
    enable: true
    # OneBot建立服务器的HOST，无特殊需求一般为 127.0.0.1
    host: 127.0.0.1
    # OneBot建立服务器的PORT，与插件的端口要对应
    port: 5700
    # OneBot服务器 Token ,一般不动
    token: ""
    # OneBot 上报的地址，即插件服务器地址
    post_url: 
    # OneBot 上报的 Secret，一般不填
    secret: ""
    # 等待响应时间，一般不动
    time_out: 0
    # OneBot上报格式，可为 string 或 array ，一般不动
    post_message_format: string

```

</details>

6) 每个姬气人都可以设置多个 正向WS 反向WS HTTP 服务，实在不懂[加群](https://jq.qq.com/?_wv=1027&k=PVW9Ol8b)问或者提 [issue](https://github.com/Yiwen-Chan/OneBot-YaYa/issues) 

7) 再次重启先驱框架（热重载什么的咕了）

- 注：不要使用`重载插件`功能，否则会导致框架闪退，此为框架与go不兼容问题
