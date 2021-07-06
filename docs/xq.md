# 先驱獭

1. 下载[先驱框架（测试版）](http://api.xianqubot.com/index.php?newver=beta)与[OneBot-YaYa](https://github.com/Yiwen-Chan/OneBot-YaYa/releases) 并解压

2. 解压先驱框架到文件夹，并运行`先驱.exe`，待相关文件生成完毕后，将`OneBot-YaYa.XQ.dll`放入`.\Plugin`，重启先驱框架

3. 切到`账号管理`界面登录机器人账号

4. 从獭窝下载配置文件并替换`.\OneBot\config.yml`（客户端选择YaYa）

<details><summary>或根据实际情况编辑<font color="orange"><b>.\OneBot\config.yml</b>></font>文件</summary>
1. `master`改为`自己的QQ号`
2. `bots` --> `bot`改为在獭獭后台申请的`姬气人QQ`
3. `bots` --> `websocket_reverse` --> `name` 改为`獭獭`
4. `bots` --> `websocket_reverse` --> `enable` 改为`true`
5. `bots` --> `websocket_reverse` --> `url` 改为獭獭后台申请姬气人窝所在的`网址`,有下面四种情况：
```
主窝 ws://xn--v9x.net:80/ws
笔窝 ws://bot.pencilss.top/ws
风窝 ws://botapi.dead-war.cn:443/ws
鸡窝 ws://tata.guomie.club/ws
```
6. `bots` --> `websocket_reverse` --> `access_token` 改为獭獭后台申请时所填的`token`

</details>


<details><summary>5. 详细的配置文件说明</summary>

```yaml
# 版本
version: 1.0.5
# 主人QQ号
master: 12345678
# 是否开启DEBUG日志
debug: true
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
    # OneBot上报格式，可为 string 或 array ，一般不动
    post_message_format: string

```

</details>

6. 每个姬气人都可以设置多个 正向WS 反向WS HTTP 服务，实在不懂[加群](https://jq.qq.com/?_wv=1027&k=PVW9Ol8b)问或者提 [issue](https://github.com/Yiwen-Chan/OneBot-YaYa/issues) 

- 注：不要使用`重载插件`功能，修改保存配置文件后会自动热重载
