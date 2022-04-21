# Mirai Android+onebot-mirai

<font color="red"><b>mirai android只适用于部分Android系统</b></font>

<font color="red"><b>mirai android只适用于部分Android系统</b></font>

<font color="red"><b>mirai android只适用于部分Android系统</b></font>

经测试，基于Android8.1的flyme os 8.1.5.1A可用

### 搭建与配置

1. 下载并安装[Mirai Android](https://install.appcenter.ms/users/mzdluo123/apps/miraiandroid/distribution_groups/release)

2. 下载 [onebot-mirai](https://github.com/yyuueexxiinngg/onebot-kotlin/releases)

3. 用资源管理器定位到`onebot-mirai-0.x.x-all.jar`，open with `Mirai Android`。按照默认选项，让它自动重编译插件.

4. 启动`Mirai Android`，观察到日志

   ```
   [INFO]Successfully loaded plugin OneBot V0.x.x
   ```
	则插件加载
   
5. 从獭窝下载配置文件并替换`.\Android\data\io.github.mzdluo123/mirai.android\config\OneBot\settings.yml`（客户端选择mirai）

<details><summary>或根据注释和实际情况更改<font color="orange"><b>settings.yml</b></font>文件内容。</summary> 


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
      postUrl: ''
      postMessageFormat: string
      secret: ''
    ws_reverse: 
      # 可选，是否启用反向客户端,即是否启用獭獭
      - enable: true
        postMessageFormat: string
        # 獭窝反向WS Universal 地址
        reverseHost: 
        # 根据窝具体情况填写端口
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

</details>



5.  启动`Mirai Android`，在控制台输入

>login QQ账号 QQ密码

并回车，进行登录即可。  

---

### 自动登录

在mirai Android软件内右上角设置

