### 创建MongoDB
- `use DATABASE_NAME` 创建数据库或连接数据库
- `show dbs` 查看所有创建的数据库实例
---
### 删除MongoDB
- `db.dropDatabase()` 删除已成功连接的数据库
---
### MongoDB创建集合
- `db.createCollection(name, options)` 手动创建集合
---
### MongoDB删除集合
- `db.collection.drop()` 如果成功删除选定集合，则 drop() 方法返回 `true`，否则返回 `false`
---
### MongoDB插入数据
- `db.collection.insert(document)` 若插入的集合`_id`与已有集合重复，则数据库报错
- `db.collection.save(document)` 若插入的集合`_id`与已有集合重复，则更新已有集合
---
### MongoDB文档更新操作
    db.collection.update(
    <query>,
    <update>,
    {
        upsert: <boolean>,
        multi: <boolean>,
        writeConcern: <document>
    }
    )
- **query** : update的查询条件，类似sql update查询内where后面的
- **update** : update的对象和一些更新的操作符（如$,$set...）等，也可以理解为sql update查询内set后面的
- **upsert** : 可选，这个参数的意思是，如果不存在update的记录，是否插入objNew,true为插入，默认是false，不插入
- **multi** : 可选，mongodb 默认是false,只更新找到的第一条记录，如果这个参数为true,就把按条件查出来多条记录全部更新
- **writeConcern** :可选，抛出异常的级别
---
### MongoDB文档删除操作
    db.collection.remove(
    <query>,
    {
        justOne: <boolean>,
        writeConcern: <document>
    }
    )
- **query** :（可选）删除的文档的条件
- **justOne** : （可选）如果设为 true 或 1，则只删除一个文档，如果不设置该参数，或使用默认值 false，则删除所有匹配条件的文档
- **writeConcern** :（可选）抛出异常的级别
---
### MongoDB查询操作
- `db.collection.find(query, projection)`
---
### MongoDB条件操作符
- (>) 大于 - `$gt`
- (<) 小于 - `$lt`
- (>=) 大于等于 - `$gte`
- (<=) 小于等于 - `$lte`
- (!=) 不等于 - `$ne`