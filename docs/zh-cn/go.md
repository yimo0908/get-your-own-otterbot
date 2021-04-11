# cqhttp-go

### 搭建

1. 先请自行下载[`cqhttp-go`](https://github.com/Mrs4s/go-cqhttp/releases)

2. 新建一个文件夹(以英文命名, eg. `tata`)，将`go-cqhttp.exe`放入其中并运行，使其自动生成框架相关文件和文件夹，然后关闭`go-cqhttp`,从獭窝下载配置文件并替换`.\config.yml`（客户端选择Go-cqhttp）（**还没实装**）

<details><summary>或根据注释及本文档编辑（只需要在意带注释的字段，其余字段请不要更改）</summary>

```yaml
# go-cqhttp 默认配置文件

account: # 账号相关
  uin: 1233456 # 机器人的QQ账号
  password: '' # 机器人的qq密码，密码为空时使用扫码登录
  encrypt: false
  status: 0      # 在线状态 请参考 https://github.com/Mrs4s/go-cqhttp/blob/dev/docs/config.md#在线状态
  relogin:
    disabled: false
    delay: 3
    interval: 0
    max-times: 0
  use-sso-address: true

heartbeat:
  disabled: false # 是否开启心跳事件上报
  # 心跳频率, 单位秒
  # -1 为关闭心跳
  interval: 5

message:
  post-format: string
  ignore-invalid-cqcode: false
  force-fragment: false
  fix-url: false
  proxy-rewrite: ''
  report-self-message: false
  remove-reply-at: false
  extra-reply-data: false

output:
  # 日志等级 trace,debug,info,warn,error
  log-level: warn
  # 是否启用 DEBUG
  debug: false # 开启调试模式

default-middlewares: &default
  # 访问密钥, 即申请獭獭时的token
  access-token: ''
  filter: ''
  rate-limit:
    enabled: false
    frequency: 1
    bucket: 1

servers:
  - http:
      # 是否关闭正向HTTP服务器
      disabled: false
      host: 127.0.0.1
      port: 5700
      timeout: 5
      middlewares:
        <<: *default
      # 反向HTTP POST地址列表
      post:
      #- url: '' # 地址
      #  secret: ''           # 密钥
      #- url: 127.0.0.1:5701 # 地址
      #  secret: ''          # 密钥

  # 正向WS设置
  - ws:
      # 是否禁用正向WS服务器
      disabled: true
      # 正向WS服务器监听地址
      host: 127.0.0.1
      # 正向WS服务器监听端口
      port: 6700
      middlewares:
        <<: *default

  - ws-reverse:
      # 是否禁用当前反向WS服务
      disabled: true
      # 反向WS Universal 地址
      # 主窝：
      # 笔窝：ws://bot.pencilss.top/ws/
      # 风窝：wss://botapi.dead-war.cn:443/ws/
      universal: ws://your_websocket_universal.server
      api: ws://your_websocket_api.server
      event: ws://your_websocket_event.server
      # 重连间隔 单位毫秒
      reconnect-interval: 3000
      middlewares:
        <<: *default
  - pprof:
      disabled: true
      host: 127.0.0.1
      port: 7700

  # 可添加更多
  #- ws-reverse:
  #- ws:
  #- http:
  #- pprof:

database:
  leveldb:
    enable: true

```


</details>

3. 保存后启动`go-cqhttp.exe`即可。  





### 事件过滤器

关于`事件过滤器启动失败: open filter.json: The system cannot find the file specified.`报错

一般不用管，若要启用事件过滤器，请看[相关文档](https://github.com/Mrs4s/go-cqhttp/blob/a417ff08818650cc101e612d82c61d58eef88713/docs/EventFilter.md)





### 设备信息 `device.json`文件

只需要关心 `protocol` 字段: 

| 值   | 类型  | 登录状态 | 限制                                           |
| ---- | --------|----- | ---------------------------------------------- |
| 0   | iPad          | 苹果平板在线 | 无 |
| 1    | Android Phone| 安卓手机在线 | 无法接收新版表情如 `/吃瓜`、`/汪汪`, 会自动转换为字符串          |
| 2 | Android Watch | 安卓手表在线 | 除`Android Phone`的限制外, 无法接收 `notify` 事件、无法接收口令红包、无法接收撤回消息 |
| 3 | MacOS | 苹果电脑在线 | 无 |


> 注意, 根据协议的不同, 各类消息有所限制
>
> 更改`protocol`字段后可能需要重新验证设备锁
