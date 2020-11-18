# onebot-kotlin

### 搭建与配置

1) 下载并安装[`jre (Java SE Runtime Environment 8)`](https://www.oracle.com/java/technologies/javase-jre8-downloads.html)或[`Java SE Development Kit 11.0.9`](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)或[`Java SE Development Kit 15`](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html)

2) 下载[onebot-kotlin](https://github.com/yyuueexxiinngg/onebot-kotlin/releases)

3) 在该目录下打开cmd或powershell，运行`java -jar onebot-kotlin-x.x.x-.jar`指令，待其生成相关文件。

4) 复制以下代码并根据注释和实际情况更改`.\config\OneBot\settings.yml`文件内容。

```yaml
# 本文件只测试了主窝 食材村(笔窝) 风窝 鸡窝，其他窝不一定适用，请自行尝试
# Debug日志输出选项
debug: false
# 图片、语音下载代理设置
proxy: ''
bots: 
  # 要进行配置的QQ号
  1234567890: 
    # 是否缓存所有收到的图片
    cacheImage: true
    # 是否缓存所有收到的语音
    cacheRecord: true
    heartbeat: 
      # 是否发送心跳包
      enable: true
      # 心跳包发送间隔，单位ms
      interval: 1500
    http: 
      enable: false
      host: 0.0.0.0
      port: 5700
      accessToken: ''
      # 事件及数据上报URL,即塔塔露提供的url
      postUrl: ''
      postMessageFormat: string
      secret: ''
    ws_reverse: 
      # 可选，是否启用反向客户端,即是否启用獭獭
      - enable: true
        postMessageFormat: string
        # 主窝 xn--v9x.net
        # 食材村（笔窝）bot.pencilss.top
        # 风窝 temp.dead-war.cn
        # 鸡窝 tata.guomie.club
        reverseHost: 
        # 主窝、食材村(笔窝)和鸡窝填80，风窝填8002
        reversePort: 
        # 访问口令，獭窝申请的时候的token
        accessToken: 
        reversePath: /ws
        reverseApiPath: /api
        reverseEventPath: /event
        useUniversal: true
        useTLS: false
        reconnectInterval: 3000
      # 可选，是否启用反向客户端2，可用于配置nonebot/hoshinobot等
      - enable: false
        postMessageFormat: string
        reverseHost: 127.0.0.1
        reversePort: 8080
        accessToken: reversePath
        reversePath: /ws
        reverseApiPath: /api
        reverseEventPath: /event
        useUniversal: true
        useTLS: false
        reconnectInterval: 3000
    ws: 
      # 可选，是否启用正向客户端
      enable: false
      postMessageFormat: string
      wsHost: 0.0.0.0
      wsPort: 6700
      accessToken: ''

```

5)  保存后在控制台输入

>login QQ账号 QQ密码

并回车，进行登录即可。  