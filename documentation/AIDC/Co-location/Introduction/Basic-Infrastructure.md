# 系统架构
云数据库 RDS 默认提供主从高可用架构，同时我们也提供单可用区部署和多可用区部署两种方式：

## 单可用区部署

![5a9e4356N131f1eb3.png](https://img1.jcloudcs.com/cms/a8b79d24-7f2b-44a5-85ff-178fd000c71320180319132608.png)

## 多可用区部署

![5a9e4352N63d77d0d.png](https://img1.jcloudcs.com/cms/26880449-0a8f-4d26-a0ab-0fc8da77828420180319132619.png)

## 架构解析
* DNS：域名解析服务，在内网我们是通过域名方式访问云数据库 RDS 实例。
* DMS：数据库管理服务，提供了一个 WEB 管理界面，方便您进行一些云数据库实例的简单管理操作。
* 控制台：京东云控制台服务，提供云数据库 RDS 的管理界面。
* 主节点，从节点：默认主节点对外提供服务，从节点作为容灾实例存在；当主节点不能提供服务的时候，从节点会被提升为新的主节点，从而保证用户业务不中断。
* 监控服务：收集云数据库 RDS 实例信息和物理机信息。
* 账号管理服务：负责云数据库 RDS 实例账号的创建，删除，授权操作。
* 库管理服务：负责云数据库 RDS 实例库的创建，删除，授权操作。
* 备份服务：自动定时备份，支持用户自定义备份。
* 性能优化服务：收集 RDS 慢日志信息，供您进行分析和系统优化。
* SQL 审计：负责收集 SQL 执行语句，作为安全审计使用。
