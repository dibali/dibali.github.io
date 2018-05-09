---
title: mysql
date: 2018-4-27 18:06:24
tags:
---

## what型语言：SQL三种类型
```
数据操作语言：DML is Data Manipulation Language statements.  SQL中处理数据等操作统称为数据操纵语言 增删改查
数据定义语言：DDL is Data Definition Language statements.  用于定义和管理SQL 数据库中的所有对象的语言
            (建设者的角度,建表,建库,建视图 等等, 15%)
数据控制语言: DCL is Data Control Language statements.  用来授予或回收访问数据库的某种特权，并控制数据库操纵事务发生的时间及效果，
            对数据库实行监视等(管理员角度,DBA[数据库管理员],5%) 这个用户是否有权限建表,等
```

## 子查询
```
where型子查询：select goods_id,goods_name from goods where goods_id=(select max(goods_id) from goods);
from型子查询：select goods_id,goods_name,cat_id from (select goods_id,cat_id,goods_name from goods
            order by cat_id asc,goods_id desc) as tmp group by cat_id
exist型子查询：select * from category where exists (select * from goods where category.cat_id=goods.cat_id);
```

## dd
