# 查看域名对应的公网IP
## 使用ping命令
```sh
% ping net10010.cn
PING net10010.cn (198.18.0.28): 56 data bytes
```
198.18.0.0 - 198.19.255.255 是一个特殊的保留地址范围，属于 Benchmark Testing（基准测试）用途。这类地址不会在互联网上路由，通常被用于网络设备测试或内部环境。在你的网络环境中，可能存在代理服务，导致域名解析被指向本地测试地址。

> 的确由于我的电脑上开启了VPN代理，导致域名解析的IP地址不是正确的公网IP。当我关闭了VPN代理服务之后，再次执行ping命令，得到的如下正确的结果：

```sh
% ping net10010.cn
PING net10010.cn (8.125.25.12): 56 data bytes
```
这次解析得到的 IP 地址是 8.125.25.12，这是一个有效的公网 IP 地址。

