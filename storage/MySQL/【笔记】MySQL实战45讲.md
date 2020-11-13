# 日志

大概分为六种：

- 重做日志（redo log）：用于事务的持久化，防止DB意外宕机，导致事务的修改丢失
- 回滚日志（undo log）：用于实现事务的隔离性，read committed，repeatable read
- 二进制日志（bin log）： 用于记录DB的变更
- 错误日志（error log）
- 慢查询日志（slow query log）
- 一般查询日志（general log）
- 中继日志（relay log）

## redo log





# 长事务

- 会导致undo log很大
- 会占用锁资源
- 应该尽量避免
- 查询长事务

```sql
--  查询超过60s的事务
select * from information_schema.innodb_trx where 
```









# 简介

- binlog 二进制日志

- 记录了数据库的变更信息，每个变更封装成一个"event"

- 主要用于两方面：

  - 用于从库复制

  - 用于从某个时间点恢复数据

- 主要有两种类型的binlog

  - Statement-based logging: 
  - Row-based logging: 



# 使用

查询binlog相关配置

```sql
show variables like "%log_bin%";

show variables like "%binlog%"
```



开启

```shell

```



# binlog结构







# Event结构







# 参考



