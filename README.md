### 1135-CobaltStrike-ToolKit

#### Malleable C2 Files

Cobalt Strike的Malleable C2配置文件，被设计用来对抗流量分析。

Cobalt Strike的Malleable C2配置文件，定义了 victim 与 团队服务器 之间的C2通信流量的“通信格式规范和方式”。

通过将C2流量伪装成正常流量。以尽量避免被NIDS报警、SOC系统安全运营人员等发现异常流量。


具体说明

|Malleable C2配置文件|描述|
|:-------------:|-----|
|malleable_C2_jQuery_c2.3.11_CN_cdn.bootcss.com.txt|伪装成web流量 浏览器与服务器之间的jQuery_c2.3.11.js相关流量 具体参考 [APT级的全面免杀与企业纵深防御体系的对抗 - 先知社区](https://xz.aliyun.com/t/4191)|
