# dockerimage-consul

**警告**: ⚠️ 本项目并没有经过严格测试，不可用于生产环境。

### 单节点

```yaml
version: "3.7"

services:
  consul-server:
    image: "registry.cn-shanghai.aliyuncs.com/yingzhuo/consul:1.6.2"
    container_name: "consul"
    hostname: "consul"
    network_mode: host
    ports:
      - "8500:8500"
      - "8600:8600"
    command:
      - "consul"
      - "agent"
      - "-server=true"
      - "-bootstrap-expect=1"
      - "-client=0.0.0.0"
      - "-data-dir=/var/tmp"
      - "-advertise=10.211.55.3"    # 广播地址
      - "-ui"
```
