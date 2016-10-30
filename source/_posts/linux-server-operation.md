---
title: 服务器工作相关及常用命令操作备忘
---

# 基本操作
1. 屏蔽端口
```bash
iptables -A INPUT -p tcp --dport 443 -j REJECT
```
2. 修改DNS
```bash
vim /etc/resolv.conf
```
```
nameserver 114.114.114.114
nameserver 8.8.8.8
```
<!-- more -->

# Postgresql 相关操作
1. 启动|关闭|重启服务
```bash
/usr/local/pgsql/bin/pg_ctl -D /postgres/data -l logfile start|stop|restart
```

2. 进入数据库
```bash
/usr/local/pgsql/bin/psql -U postgres
```

3. 列出所有数据库
```bash
\l
```

4. 选用某个数据库
```bash
\c rms_mlt_oa
```

5. 导出数据库
```bash
/usr/local/pgsql/bin/pg_dump -U postgres -f db.sql  rms_mlt_oa
```

6. 导入数据库
```bash
psql -U postgres(用户名)  数据库名(缺省时同用户名) < C:\fulldb.sql
```