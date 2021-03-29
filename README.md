## 1135-CobaltStrike-ToolKit

### Malleable C2 Files

Cobalt Strike的Malleable C2配置文件，被设计用来对抗流量分析。

Cobalt Strike的Malleable C2配置文件，定义了 victim 与 团队服务器 之间的C2通信流量的“通信格式规范和方式”。

通过将C2流量伪装成"正常流量"。以避免直接被NIDS、SOC系统识别为异常流量，可能迷惑安全运营人员。


具体说明

|Malleable C2 profile|cs version|描述|
|:-----:|--|--|
|jquery.xxx.js_CN_cdn.bootcss.com_for_cs3.14_.txt|3.12 3.14|伪装成正常HTTP流量: 浏览器与web服务器之间的流量. |
|jquery.xxx.js_code.bootcdn.net_for_cs4.0_.txt| 4.0 | 伪装成正常HTTP流量: 浏览器与web服务器之间的流量. |

建议自行修改 Malleable C2 profile.

* 其他参考
  * [APT级的全面免杀与企业纵深防御体系的对抗 - 先知社区](https://xz.aliyun.com/t/4191) 
  * https://github.com/threatexpress/malleable-c2

---

### AggressorScripts

AggressorScripts - 修改或扩展Cobalt Strike 3.* 的客户端功能(可实现自定义菜单创建，日志记录，权限维持等)。

更多参考官方介绍[Aggressor Script Tutorial and Reference](https://www.cobaltstrike.com/aggressor-script/index.html)

具体说明

|filename|opsec|desc|demo|
|:-----:|--|------|-------|
|BeaconNote.cna|1|某个Beacon首次上线时 设置这个Beacon的note为`Beacon ID + 首次上线时间` |`bid: 86985 Established: 11/13/2019 16:50:19 (CST)`|
|BeaconNotify.cna|1|某个Beacon首次上线时 将这个Beacon的完整信息都发送到指定的Slack Channel [配置你的Slack webhooks](https://api.slack.com/messaging/webhooks)|`host/User/beaconID/os/ver/PID/external IP/internal IP...`|
|LoopDo.cna|0|每隔x分钟执行一次操作 | 按时执行 自定义cmd命令/屏幕截图/logonpasswords/...|


#### 补充说明

teamserver服务器日志 - 文件夹`cobaltstrike/logs/{date}/{ip}`

|Log Type|ext|location|
|:-----:|-|------------|
|Beacon命令行 所有内容|.log|`/cobaltstrike/logs/191107/10.10.13.19/becon_71256.log`|
|屏幕截图|.jpg|`/cobaltstrike/logs/191107/10.10.13.19/screenshots/screen_050658_87924.jpg`|


#### Others

|author/filename|opsec|desc|demo|
|:-----:|--|------|-------|
| [outflanknl/Ps-Tools](https://github.com/outflanknl/Ps-Tools) PS-Tools.cna | ? | 列出进程的详细信息 |5种命令`psx psk psc psm psh psw` |
| https://github.com/rsmudge/ElevateKit | ? | [官方推荐](https://www.cobaltstrike.com/help-beacon) 多个较新的提权漏洞exp.  版本要求: for Cobalt Strike 3.6 and later. | |
