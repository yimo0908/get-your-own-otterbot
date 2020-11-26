# 一键包

### 搭建与配置

1) 阅读`读我！.txt`

2) 解压一键包，并运行run.cmd 。等待其生成相关文件并关闭控制台。

3) 复制以下代码并根据注释和实际情况更改`.\config\OneBot\settings.yml`文件内容。

```yaml
# 本文件只测试了主窝 食材村(笔窝) 风窝 鸡窝，其他窝不一定适用，请自行尝试
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

​      
​      

### 自动登录与登录协议

自行更改`.\config\Console`目录下的`AutoLogin.yml`文件

---

### 日志

新版`console`内置了简单修改日志打印等级的配置, 因此弃用自定义`Logger`

- `OneBot`配置项中`debug`项作废, 修改此项不会产生任何作用
- 开启Debug打印的配置请修改`console`本身的配置, 位于`config/Console/Logger.yml`
  - 可将`defaultPriority: INFO`修改为`defaultPriority: DEBUG`或以上开启所有**mirai及所有插件**的Debug日志输出
  - **或在`loggers`项下新增`OneBot: DEBUG`或以上单独开启本插件的Debug日志输出**