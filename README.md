<img src="http://wx3.sinaimg.cn/mw690/56432499gy1fg6kzannujj20jc06rjsj.jpg">

# 后台玩家接口

## 1. 查询玩家列表
### 1.1 玩家列表
查询玩家列表
### 1.2 请求说明
> 请求方式：GET<br>
请求URL ：http://127.0.0.1/user/list

### 1.3 example
curl  http://127.0.0.1/user/list


### 1.5 返回结果
```json
{

    "user_list": [
        {
            "id": 1,
            "name": "玩家a",
            "lasttime": 1499913750,
        },
        {
            "id": 2,
            "name": "玩家b",
            "lasttime": 1499913750,
        },
        {
            "id": 3,
            "name": "玩家c",
            "lasttime": 1499913750,
        }
    ]
}
```
#### 字段说明
字段       |字段类型       |字段说明
------------|-----------|-----------
id       |int        |玩家id
name       |staring        |玩家姓名
lasttime       |int        |玩家最后登录时间




## 2. 查询玩家信息
### 2.1 查询玩家信息
查询单个玩家信息
### 2.2 请求说明
> 请求方式：POST<br>
请求URL ：http://127.0.0.1/user/info

### 2.3 example
curl -d '{"id":10}' http://127.0.0.1/user/info

### 2.4 请求参数
字段       |字段类型       |字段说明       |填写
------------|-----------|-----------|-----------
id       |int        |玩家id       |必填


### 2.5 返回结果
```json
{
  "id": 1,
  "name":"玩家A",
  "server": "测试服",
  "level":10,
  "gem":10,
  "gold":10,
  "viplevel":"5",
  "estoppel":200,
  "ban":0,
  "usercp":10,
  "exp":1000,
  "labor_union":"渣渣工会",
  "score":200,
}
```
#### 字段说明
字段       |字段类型       |字段说明
------------|-----------|-----------
id       |int        |玩家id
name       |string        |玩家姓名
server       |sting        |服务器名称
level       |int        |玩家等级
gem       |int        |钻石
gold       |int        |黄金
viplevel       |int       |vip等级
estoppel       |int 	|玩家禁言时间 0为没有 9999为永久
ban       |int 	|玩家封停时间 0为没有 9999为永久
usercp    |int 	|魅力值
exp    |int 	|经验值
labor_union    |string 	|渣渣工会
score    |int 	|玩家积分


## 3. 禁言玩家
### 3.1 禁言玩家信息
禁言一名玩家
### 3.2 请求说明
> 请求方式：POST<br>
请求URL ：http://127.0.0.1/user/estoppel

### 3.3 example
curl -d '{"id":10,"end_time":1499913750}' http://127.0.0.1/user/estoppel

### 3.4 请求参数
字段       |字段类型       |字段说明       |填写
------------|-----------|-----------|-----------
id       |int        |玩家id       |必填
end_time       |int        |结束时间       |必填

### 2.5 返回结果
```json
{
  "result": 0
}
```
#### 字段说明
字段       |字段类型       |字段说明
------------|-----------|-----------
result       |int        |返回结果0为成功 否则返回错误（详见error规范）



## 4. 封停玩家
### 4.1 封停一名玩家
封停一名玩家
### 4.2 请求说明
> 请求方式：POST<br>
请求URL ：http://127.0.0.1/user/ben

### 4.3 example
curl -d '{"id":10,"end_time":1499913750}' http://127.0.0.1/user/ben

### 4.4 请求参数
字段       |字段类型       |字段说明       |填写
------------|-----------|-----------|-----------
id       |int        |玩家id       |必填
end_time       |int        |结束时间       |必填


### 4.5 返回结果
```json
{
  "result": 0
}
```
#### 字段说明
字段       |字段类型       |字段说明
------------|-----------|-----------
result       |int        |返回结果0为成功 否则返回错误（详见error规范）


## 5. 禁言玩家列表
### 5.1 禁言玩家列表
查询禁言玩家列表
### 5.2 请求说明
> 请求方式：GET<br>
请求URL ：http://127.0.0.1/user/estoppel_list

### 5.3 example
curl  http://127.0.0.1/user/estoppel_list


### 5.5 返回结果
```json
{

    "user_list": [
        {
            "id": 1,
            "name": "玩家a",
            "end_time": 1499913750,
        },
        {
            "id": 2,
            "name": "玩家b",
            "end_time": 1499913750,
        },
        {
            "id": 3,
            "name": "玩家c",
            "end_time": 1499913750,
        }
    ]
}
```
#### 字段说明
字段       |字段类型       |字段说明
------------|-----------|-----------
id       |int        |玩家id
name       |staring        |玩家姓名
end_time       |int        |玩家禁言结束时间

## 6. 封停玩家列表
### 6.1 封停玩家列表
查询封停玩家列表
### 6.2 请求说明
> 请求方式：GET<br>
请求URL ：http://127.0.0.1/user/ben_list

### 5.3 example
curl  http://127.0.0.1/user/ben_list


### 5.5 返回结果
```json
{

    "user_list": [
        {
            "id": 1,
            "name": "玩家a",
            "end_time": 1499913750,
        },
        {
            "id": 2,
            "name": "玩家b",
            "end_time": 1499913750,
        },
        {
            "id": 3,
            "name": "玩家c",
            "end_time": 1499913750,
        }
    ]
}
```
#### 字段说明
字段       |字段类型       |字段说明
------------|-----------|-----------
id       |int        |玩家id
name       |staring        |玩家姓名
end_time       |int        |玩家封停结束时间



### 错误状态码
#### 如果出现错误，返回错误信息
状态码       |说明
------------|-----------
1000       |认证错误信息！
1001       |参数错误
1002       |id不存在
1003       |玩家已经被禁言
1004       |玩家已经被封停


```json
{
  "err": 1001,
  "msg":"参数错误"
}
```
