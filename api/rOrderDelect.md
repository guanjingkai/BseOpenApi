### 接口描述
删除预支付单
### 请求地址
> http(s)://api.huishouyin.cn/rorder/delect

### 请求方式
`POST`
### 请求参数
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|app_id|String|是|32|应用ID|
|sign|String|是|32|签名 [签名规则](/main/sign)|
|sign_type|String|是|32|签名加密类型 `MD5` `RSA`|
|order_id|String|否|64|原支付业务单号|


### 请求事例
```javascript
{
    app_id:'app_id',
    sign:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
    sign_type:'MD5',
    order_id:'2017102100151091',
}
```
### 响应参数
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|status|int|是|1|1000 请求成功 |
|msg|String|是|1|应用ID|
|app_id|String|是|32|订单所属app|
|r_no|String|是|64|联富通交易流水号|
|order_id|String|是|128|原支付业务单号|
### 响应事例
```javascript
{
    code:1000,
    msg:'查询成功',
    data:{
        r_no:'2017102100151091',
        order_id:'2017102100151091',
        app_id:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
    }
}
```
### 异常响应
|名称|描述|
|-----|-----|
|`4001`|原订单不存在定|
### 异常响应事例
```javascript
{
    code:4001,
    msg:'原订单不存在',
    data:{
        
    }
}
```