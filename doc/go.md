# cqhttp-go

#### 1.先请自行下载 

#### 2.新建一个文件夹(以英文命名, eg. `tata`)，将`go-cqhttp.exe`放入其中并运行，使其自动生成框架相关文件和文件夹，然后关闭`go-cqhttp`，编辑`config.json`



````json
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
	"post_message_format": "string",
	"ignore_invalid_cqcode": false,
	"force_fragmented": true,
	"heartbeat_interval": 5,
	"http_config": {
		"enabled": true,
		"host": "0.0.0.0",
		"port": 5700,
		"timeout": 5,
		"post_urls": {"url:port": "secret"}
	},
	"ws_config": {
		"enabled": false,
		"host": "0.0.0.0",
		"port": 6700
	},
	"ws_reverse_servers": [
		{
			"enabled": true,
			"reverse_url": "",
			"reverse_api_url": "",
			"reverse_event_url": "",
			"reverse_reconnect_interval": 3000
		}
	]
}
````



| 字段                            | 说明                                                        |
| --------------------------  | ----------------------------------------------------------- |
| uin                             | 登录用QQ号                                                  |
| password                        | 登录用密码                                                  |
| access_token                    | 同CQHTTP的 `access_token`  用于身份验证（獭獭のtoken）      |
| force_fragmented                 | 是否强制分片发送群长消息                                    |
| heartbeat_interval               | 心跳间隔时间，单位秒。小于0则关闭心跳，等于0使用默认值(5秒) |
| http_config                      | HTTP API配置                                                |
| url:port                        | post url地址（塔塔露のurl）                                 |
| secret                          | post url密码（配置塔塔露则留空）                            |
| ws_config                      | Websocket API 配置                                          |
| ws_reverse_servers              | 反向 Websocket API 配置                                     |
| reverse_url                      | 獭窝のws地址                                                |
| reverse_api_url                | 獭窝のws-api地址（可留空）                                  |
| reverse_reconnect_interval      | 獭窝のws-event地址（可留空）                                |
| reverse_reconnect_interval |       ws重连间隔                                |


>注1: 分片发送为原酷Q发送长消息的老方案, 发送速度更优/兼容性更好，但在有发言频率限制的群里，可能无法发送。关闭后将优先使用新方案, 能发送更长的消息, 但发送速度更慢，在部分老客户端将无法解析.   
>注2：关闭心跳服务可能引起断线，请谨慎关闭    



#### 3.保存后启动`go-cqhttp.exe`即可。    

### 设备信息 `device.json`文件

默认生成的设备信息如下所示: 

``` json
{
	"protocol": 0,
	"display": "xxx",
	"finger_print": "xxx",
	"boot_id": "xxx",
	"proc_version": "xxx",
	"imei": "xxx"
}
```

在大部分情况下 我们只需要关心 `protocol` 字段: 

| 值   | 类型  | 登录状态 | 限制                                           |
| ---- | --------|----- | ---------------------------------------------- |
| 0    | Android Pad | 平板在线 | 无法接收 `group_notify` 事件、无法接收口令红包 |
| 1    | Android Phone| 手机在线 | 无                                             |


> 注意, 根据协议的不同, 各类消息有所限制
>
> 更改`protocol`字段后可能需要重新验证设备锁
