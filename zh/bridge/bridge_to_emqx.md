# 其他消息中间件桥接至 EMQ X

EMQ X 完全支持 MQTT 协议，它也可以被其他 MQTT 消息中间件桥接。如下图所示，其他消息中间件在桥接到 EMQ X 时，其他消息中间件并不需要了解 EMQ X 的实现细节，只需要把 EMQ X 作为一个标准的消息中间件即可。

```
             -------------             -----------------
Client ----> |   Broker  | --Bridge--> |               |
             -------------             |     EMQ X     |
             -------------             |    Cluster    |
Client ----> |   Broker  | --Bridge--> |               |
             -------------             -----------------
```
其他消息中间件桥接至 EMQ X 的场景在实际部署中并不少见。尤其是在现网使用其他消息中间件，但是在系统扩容是发现中间件无法满足需求，但完全改变现网部署有困难的时候，或者是现网使用其他协议，想在未来迁移到 MQTT 协议，但又需要兼容现有设备的时候。在这样的场景下，使用桥接可以降低扩容和迁移难度，避免对现网有过大冲击，并对未来统一到 EMQ X 平台做好准备。  
另外，以桥接的方式，EMQ X 也可以作为远程中心节点，集中处理边缘设备消息网关/中间件上传和下发的消息。


_在本章节接下来的内容中，您将通过案例看到如何配置其他常见消息中间件到 EMQ X 的桥接。_
