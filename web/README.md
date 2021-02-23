# web端

**注意：源代码中包含Google Analytics分析代码，`index.html`, `search.html`和`resource.html`。如果自己使用，要记得去除哦**

# requirements

* tornado
* mongodb
* pymongo
* cryptography

# 导入数据

## 方法1: 自己迁移数据

1. 下载[MySQL的数据](https://t.me/mikuri520/668)
1. 导入数据到MySQL
2. 运行 `python prepare/convert_db.py`

## 方法2:使用我的导出
* [冷数据看这里](https://t.me/c/1375651700/2448)，然后导入到MongoDB
* [实时数据看这里](https://yyets.dmesg.app/data/dump.gz)，每天凌晨2点更新

# 运行

`python server.py`

# Docker

参考[这里](https://github.com/BennyThink/WebsiteRunner)

# MongoDB index

```shell
use zimuzu;

db.getCollection('yyets').createIndex({"data.info.id": 1});

db.getCollection('yyets').createIndex({"data.info.views" : -1});

db.getCollection('yyets').createIndex({"data.info.area" : 1});

db.getCollection('yyets').getIndexes();
```
