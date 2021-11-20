# **商城数据库间建表**

项目一期搭建（erhai）

1创建一个数据表空间100M 10M

2创建一个新的用户hercules-----123456,用这个用户去登录

3创建这些表----------导入sql

4创建一个web项目（po,mapper,dao,utils）--对每一个表的每一列做测试

-------DAO---------CRUD---------

### 1. **商品**表PRODUCT

| 名称                          | 描述   | 字段类型          | java类型 | 备注          |
| --------------------------- | ---- | ------------- | ------ | ----------- |
| PID                         |      | Number(11)    | Int    |             |
| PNAME                       | 标题   | Varchar2(50)  | String |             |
| PCOUNT                      | 库存   | Varchar2(50)  | String |             |
| PRICE                       | 现价   | Number(10,2)  | double |             |
| PTEXT                       | 简述   | Varchar2(100) | String |             |
| PDATE                       | 发布时间 | Date          | String |             |
| PHOTO                       | 预览照片 | Varchar2(100) | String |             |
| PBOOLEAN                    | 是否上架 | Varchar2(10)  | String | 0代表不上架1代表上架 |
| LOCATION                    | 发货坐标 | Varchar2(200) | String | （省/市）       |
| CLASSID                     | 分类id | Number(11)    | Int    |             |
| [PROMOTION](#/javascript:;) | 促销   | Varchar2(100) | String | 0非促销1促销     |

### 2. **商品详情表PRODUCTDETIAL**

| 名称          | 描述   | 字段类型           | java类型 | 备注       |
| ----------- | ---- | -------------- | ------ | -------- |
| PID         |      | Number(11)     | Int    |          |
| PDBTEXT     | 详细描述 | Varchar2(1000) | String |          |
| PPHOTO      | 预览照片 | Varchar2(1000) | String | （，号隔开照片） |
| PTEXTPHOTOS | 描述照片 | Varchar2(1000) | String |          |

### 3. **订单表ORDERS**

| 名称       | 描述   | 字段类型          | java类型 | 备注                             |
| -------- | ---- | ------------- | ------ | ------------------------------ |
| OID      |      | Number(11)    | Int    |                                |
| ODATE    | 创建时间 | Date          | String |                                |
| OBOOLEAN | 订单状态 | Varchar2(100) | String | 1待付款2待发货3待收货4待评价5待退货6退货成功7订单完成 |
| PID      | 商品ID | Number(11)    | Int    |                                |
| SITEID   | 地址ID | Number(11)    | Int    |                                |
| USERID   | 用户id | Number(11)    | Int    |                                |

### 4. **购物车表CAR**

| 名称     | 描述   | 字段类型       | java类型 | 备注  |
| ------ | ---- | ---------- | ------ | --- |
| CID    |      | Number(11) | Int    |     |
| PID    | 商品ID | Number(11) | Int    |     |
| USERID | 用户id | Number(11) | Int    |     |
| COUNT  | 数量   | Number(11) | Int    |     |

### 5. **用户表USERS**

| 名称       | 描述   | 字段类型          | java类型 | 备注     |
| -------- | ---- | ------------- | ------ | ------ |
| UID      |      | Number(11)    | Int    |        |
| NAME     |      | Varchar2(50)  | String |        |
| PASS     |      | Varchar2(50)  | String |        |
| EXT      | 个人描述 | Varchar2(500) | String |        |
| PHOTO    | 头像   | Varchar2(500) | String |        |
| AGE      |      | Number(3)     | Int    |        |
| SEX      |      | Varchar2(10)  | String | 男/女/未知 |
| LOCATION | 位置   | Varchar2(200) | String | 省/市    |
| USERCODE | 用户积分 | Number(10)    | Int    |        |

### 6. **地址表SITE**

| 名称         | 描述         | 字段类型      | java类型 | 备注 |
| ------------ | ------------ | ------------- | -------- | ---- |
| SID          |              | Number(11)    | Int      |      |
| USERID       | 用户ID       | Number(11)    | Int      |      |
| LOCATION     | 收货地址     | Varchar2(200) | String   |      |
| LOCATIONTEXT | 收货地址详情 | Varchar2(200) | String   |      |
