# Magnus

## 介绍
Magnus 是 JumpServer 的数据库安全连接组件，支持多种数据库协议，使用Golang实现，名字来源于 Dota 英雄 [猛犸](https://www.dota2.com/hero/magnus) 。

该仓库主要用于配置介绍和 Release 发布。

## 支持的功能

- [x] 安全认证
- [x] 客户端过滤
- [x] SQL 过滤
- [x] SQL 录像
- [x] SQL 阻断
- [x] SQL 复核 (X-Pack)

## 支持的数据库

- [x] MySQL 5.7/8.0+
- [x] MariaDB
- [x] PostgreSQL (X-Pack)
- [ ] SQL Server (X-Pack)
- [ ] Oracle (X-Pack)

## 要求

```
jumpserver >= v2.21.0 
```


## 配置

Magnus 的启动配置，参考 [config_example](config_example.yml)

## Docker 镜像

可根据 JumpServer 版本获取对应的镜像，例如：获取 v2.21.0 版本的镜像
```shell
docker pull jumpserver/magnus:v2.21.0
```

docker 启动

```shell
docker run -d --name jms_magnus -p 33060:33060 -p 33061:33061 -p 54320:54320  \
-v $(pwd)/config.yml:/opt/magnus/config.yml \
jumpserver/magnus:v2.21.0
```