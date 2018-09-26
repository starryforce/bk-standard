# 数据库命名规范
## 数据库名 
* 用产品或项目的名字命名；
* Pascal Case，如AdventureWork; 
* 避免使用特殊字符，如数字，下划线，空格之类；
* 避免使用缩写
## 表名
* 使用复数，Pascal Case，而复数只加在最后一个单词上如：Products，Users，UserRoles
* 避免使用特殊字符，如数字，下划线，空格之类；
* 避免使用缩写
## 列名
* 使用Pascal Case
* 避免和表名重复，避免数据类型前缀如: Int
* 避免使用缩写或者特殊字符
## 存储过程
* 用动词加表名描述操作类型
* 使用前缀：sp+{“Insert”, “Update”, “Delete”, “Get”, “Validate”,...}
## 视图
* 参考表名规则
* 用"vw"做前缀
## 触发器
* 使用"trg"前缀
* 使用操作类型+表名，如：trg_ProductsInsert
## 索引
* 使用格式如：idx_{表名}_{索引列名}_{Unique/NonUnique}_{Cluster/NonCluster}
## 主键
* 使用格式如：pk_{表名}_{主键列名}
## 外键
* 使用格式如：fk_{主表名}_{主表的列名}_{引用表名}_{引用表的列名}
## default
* 使用格式如：df_{表名}_{列名}
## 约束
* 使用格式如：ck_{表名}_{列名}
## 变量
* 参照列名规则
