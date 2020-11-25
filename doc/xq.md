# 先驱獭

1) 下载先驱框架（测试版）与[onebot-yaya](https://github.com/Yiwen-Chan/OneBot-YaYa/releases) **本插件目前只支持反向ws，即獭獭/hoshinobot/nonebot等，不支持正向ws、http**

2) 解压先驱框架到文件夹，并运行`先驱.exe`，待相关文件生成完毕后，将`OneBot-YaYa.XQ.dll`放入`.\Plugin`，重启先驱框架

3) 切到`账号管理`界面登录机器人账号

3) 复制以下代码并根据实际情况编辑`.\data\app\onebot-yaya\config.yml`文件（也可通过群聊命令进行配置）

````yaml
version: 1.0.1
# 号主QQ（用于操控子功能开关）
master: 1234567890
# 详细日志开关
debug: false
bots:
#机器人QQ号
- bot: 987654321
  cacheImage: false
  cacheRrcord: false
  # 心跳设置
  heratbeat:
    enable: true
    interval: 10000
  #正向ws，还没做
  websocket:
    enable: false
    host: 127.0.0.1
    port: 6700
    access_token: ""
    post_message_format: string
  #反向ws配置
  websocket_reverse:
    # 反向ws开关
    enable: true
    # 反向ws_url，即獭窝ws地址
    url: ws://bot.pencilss.top/ws
    api_url: ws://bot.pencilss.top/api
    event_url: ws://bot.pencilss.top/event
    use_universal_client: true
    # 申请獭獭时的token
    access_token: ""
    post_message_format: string
    reconnect_interval: 3000
  # http功能 还没做
  http:
    enable: false
    host: 127.0.0.1
    port: 5700
    post_url: http://127.0.0.1:5705/
    secret: ""
    time_out: 0
    post_message_format: string

````

4) 再次重启先驱框架