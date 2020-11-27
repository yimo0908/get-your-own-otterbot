# 先驱獭

1) 下载先驱框架（测试版）与[onebot-yaya](https://github.com/Yiwen-Chan/OneBot-YaYa/releases) 

2) 解压先驱框架到文件夹，并运行[先驱.exe](http://api.xianqubot.com/index.php?newver=beta)，待相关文件生成完毕后，将`OneBot-YaYa.XQ.dll`放入`.\Plugin`，重启先驱框架

3) 切到`账号管理`界面登录机器人账号

3) 根据实际情况及注释编辑`.\OneBot\config.yml`文件
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
- bot: 1706264393
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
    post_url: http://tataru.aoba.vip/api/cq_http_api.php?key=32ecc46c250cc31646626ebac0b0dee0
    # OneBot 上报的 Secret，一般不填
    secret: ""
    # 等待响应时间，一般不动
    time_out: 0
    # OneBot上报格式，可为 string 或 array ，一般不动
    post_message_format: string

```
4) 再次重启先驱框架
