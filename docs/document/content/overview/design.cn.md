+++
pre = "<b>1.2 </b>"
title = "设计哲学"
weight = 2
chapter = true
+++

ShardingSphere 采用 Database Plus 设计哲学，该理念致力于构建数据库上层的标准和生态，在生态中补充数据库所缺失的能力。

![ShardingSphere Architecture](https://shardingsphere.apache.org/document/current/img/overview.cn_v2.png)

## 连接：打造数据库上层标准

通过对数据库协议、SQL 方言以及数据库存储的灵活适配，快速构建多模异构数据库上层的标准，同时通过内置 DistSQL 为应用提供标准化的连接方式。

## 增强：数据库计算增强引擎

获取数据库的访问流量，并提供流量重定向（数据分片、读写分离、影子库）、流量变形（数据加密、数据脱敏）、流量鉴权（安全、审计、权限）、流量治理（熔断、限流）以及流量分析（服务质量分析、可观察性）等透明化增量功能。

## 可插拔：构建数据库功能生态

Apache ShardingSphere 的可插拔架构划分为 3 层，它们是：L1 内核层、L2 功能层、L3 生态层。

### L1 内核层

是数据库基本能力的抽象，其所有组件均必须存在，但具体实现方式可通过可插拔的方式更换。
主要包括查询优化器、分布式事务引擎、分布式执行引擎、权限引擎和调度引擎等。

### L2 功能层

用于提供增量能力，其所有组件均是可选的，可以包含零至多个组件。
组件之间完全隔离，互无感知，多组件可通过叠加的方式相互配合使用。
主要包括数据分片、读写分离、数据库高可用、数据加密、影子库等。
用户自定义功能可完全面向 Apache ShardingSphere 定义的顶层接口进行定制化扩展，而无需改动内核代码。

### L3 生态层

用于对接和融入现有数据库生态，包括数据库协议、SQL 解析器和存储适配器，分别对应于 Apache ShardingSphere 以数据库协议提供服务的方式、SQL 方言操作数据的方式以及对接存储节点的数据库类型。