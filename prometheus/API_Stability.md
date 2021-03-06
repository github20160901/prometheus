Prometheus承诺在主要版本中保持API稳定性，并努力避免破坏关键功能的变化。一些功能，即化妆品，仍在开发中，或依赖于第三方服务，不在此范围内。

对于2.x而言被认为是稳定的：

- 查询语言和数据模型
- 警报和录制规则
- 摄取博览会格式
- v1 HTTP API（由仪表板和UI使用）
- 配置文件格式（减去服务发现远程读/写，见下文）
- 规则/警报文件格式
- 控制台模板语法和语义

被认为对2.x不稳定的事情：

- 任何列为实验性或可能发生变化的功能，包括：
    - `holt_winters PromQL`函数
    - 远程读取，远程写入和远程读取端点
    - v2 HTTP和GRPC API
- 服务发现集成，`static_configs`和`file_sd_configs`除外
- 转到属于服务器一部分的API
- Web UI生成的HTML
- Prometheus本身的/ metrics端点中的度量标准
- 精确的磁盘格式。然而，潜在的变化将由Prometheus向前兼容并透明地处理

只要您没有使用标记为实验/不稳定的任何功能，通常可以在没有任何操作调整的情况下执行主要版本内的升级，并且任何事情都会破坏的风险很小。任何重大更改都将在发行说明中标记为`CHANGE`。
