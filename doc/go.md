# cqhttp-go

#### 1.先请自行下载[`cqhttp-go`](https://github.com/Mrs4s/go-cqhttp/releases)

#### 2.新建一个文件夹(以英文命名, eg. `tata`)，将`go-cqhttp.exe`放入其中并运行，使其自动生成框架相关文件和文件夹，然后关闭`go-cqhttp`,从獭窝下载配置文件并替换`.\config.hjson（客户端选择Go-cqhttp）

<details><summary>或根据注释及本文档编辑</summary>

```json
{
	"uin": 0,
	"password": "",
	"encrypt_password": false,
	"password_encrypted": "",
	"enable_db": true,
	"access_token": "",
	"relogin": {
		"enabled": true,
		"relogin_delay": 3,
		"max_relogin_times": 0
	},
	"_rate_limit": {
		"enabled": false,
		"frequency": 1,
		"bucket_size": 1
	},
	"ignore_invalid_cqcode": false,
	"force_fragmented": false,
	"heartbeat_interval": 0,
	"http_config": {
		"enabled": false,
		"host": "0.0.0.0",
		"port": 3500,
		"timeout": 0,
		"post_urls": {}
	},
	"ws_config": {
		"enabled": false,
		"host": "0.0.0.0",
		"port": 6700
	},
	"ws_reverse_servers": [
		{
			"enabled": true,
			"reverse_url": "ws://xn--v9x.net/ws",
			"reverse_api_url": "ws://xn--v9x.net/api",
			"reverse_event_url": "ws://xn--v9x.net/event",
			"reverse_reconnect_interval": 3000
		}
	],
	"post_message_format": "string",
	"use_sso_address": false,
	"debug": false,
	"log_level": "",
	"web_ui": {
		"enabled": true,
		"host": "127.0.0.1",
		"web_ui_port": 9999,
		"web_input": false
	}
}
```

| 字段                            | 说明                                                        |
| --------------------------  | ----------------------------------------------------------- |
| uin                             | 登录用QQ号                                                  |
| password                        | 登录用密码                                                  |
| access_token                    | 同CQHTTP的 `access_token`  用于身份验证（獭獭のtoken）      |
| force_fragmented                 | 是否强制分片发送群长消息                                    |
| heartbeat_interval               | 心跳间隔时间，单位秒。小于0则关闭心跳，等于0使用默认值(5秒) |
| http_config                      | HTTP API配置                                                |
| ws_config                      | Websocket API 配置                                          |
| ws_reverse_servers              | 反向 Websocket API 配置                                     |
| reverse_url                      | 獭窝のws地址（如`ws://bot.pencilss.top/ws`）                 |
| reverse_api_url                | 獭窝のws-api地址（如`ws://bot.pencilss.top/api`,可留空）    |
| reverse_reconnect_interval      | 獭窝のws-event地址（如`ws://bot.pencilss.top/event`,可留空） |
| reverse_reconnect_interval |       ws重连间隔                                |


>注1: 分片发送为原酷Q发送长消息的老方案, 发送速度更优/兼容性更好，但在有发言频率限制的群里，可能无法发送。关闭后将优先使用新方案, 能发送更长的消息, 但发送速度更慢，在部分老客户端将无法解析   
>注2：关闭心跳服务可能引起断线，请谨慎关闭    
>注3：缝合塔塔露请打开http功能，在`post_url`字段里按`{"http:tataru.aoba.vip......": ""}`填上相关链接。注意http_config的host与port不得被占用；且heartbeat_interval需要改成具体数值，防止报错。



</details>

#### 3.保存后启动`go-cqhttp.exe`即可。  





### 关于`事件过滤器启动失败: open filter.json: The system cannot find the file specified.`报错

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
