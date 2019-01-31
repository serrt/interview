## 商城网站

前后台 UI 统一采用 [Bootstrap 4](http://code.z01.com/v4/)

### 后台

- 后台管理员(增，删，改，查)
- 查看注册的会员
- 管理商品(增，删，改，查)
- 查看会员下的订单

### 前台

- 会员登陆，注册
- 查看商品列表，商品详细，搜索商品
- 购买商品下单

### 数据表

### 管理员(admin_users)


| 字段名  | 类型 | 注释 |
| --------  | --------- | ------- |
| id  | int | 主键自增 |
| username  | string(100) | 登陆名 |
| password  | string(255) | 登陆密码 |
| created_at  | timestamp | 创建时间 |
| updated_at  | timestamp | 更新时间 |


### 会员(users)


| 字段名  | 类型 | 注释 |
| ------------  | ------------ | ------- |
| id  | int | 主键自增 |
| username  | string(100) | 登陆名 |
| password  | string(255) | 登陆密码 |
| email  | string(100) | 登陆邮箱 |
| created_at  | timestamp | 注册时间 |
| updated_at  | timestamp | 更新时间 |

### 商品(goods)


| 字段名  | 类型 | 注释 |
| ------------ | ------------ | ------- |
| id  | int | 主键自增 |
| name  | string(100) | 商品名称 |
| cover_img  | string(255) | 封面图 |
| price  | int | 价格 |
| content  | text | 内容 |
| created_at  | timestamp | 创建时间 |
| updated_at  | timestamp | 更新时间 |

### 订单(orders)


| 字段名  | 类型 | 注释 |
| ------------ | ------------ | ------- |
| id  | int | 主键自增 |
| user_id  | int | 下单用户 |
| price  | int | 订单总价格 |
| remarks  | text | 下单备注 |
| created_at  | timestamp | 下单时间 |
| updated_at  | timestamp | 更新时间 |

### 订单商品(order_goods)


| 字段名  | 类型 | 注释 |
| ------------ | ------------ | ------- |
| id  | int | 主键自增 |
| order_id  | int | 订单id |
| goods_id  | int | 商品id |
| goods_price  | text | 商品价格 |
| cover_img  | string(255) | 商品封面图 |
| created_at  | timestamp | 创建时间 |
| updated_at  | timestamp | 更新时间 |

## 扩展

- 商品详细采用编辑器, 商品增加多图上传
- 后台统计(注册会员，商品购买数量，会员下单数量)

