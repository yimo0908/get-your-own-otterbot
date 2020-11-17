# mcl+cqhttp

### 搭建与配置

1) 下载并安装[`Java SE Development Kit 11.0.9`](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)

2) 下载[mcl](https://github.com/iTXTech/mirai-console-loader) 与 [cqhttp-mirai(onebot-mirai)](https://github.com/yyuueexxiinngg/cqhttp-mirai/releases)

3) 解压mcl，并运行mcl.cmd (也可以在该目录下打开cmd或powershell，运行`java -jar mcl.jar`或` ./mcl`指令)。等待其生成相关文件并关闭mcl。将`onebot-mirai-x.x.x-all.jar`放入目录`.\plugins`。

4) 重启mcl，复制以下代码并根据注释和实际情况更改`.\config\OneBot\settings.yml`文件内容。

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

​      
​      

### 自动登录

自行更改`\config\Console`文件夹里的`AutoLogin.yml`

`plainPasswords`里  
`123456654321`替换为qq号，`example`替换为qq密码

```yaml
plainPasswords: 
	123456654321: example
md5Passwords: 
	123456654321: 1A 79 A4 D6 0D E6 71 8E 8E 5B 32 6E 33 8A E5 33
```