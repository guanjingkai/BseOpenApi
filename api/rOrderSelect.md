### 接口描述
通过`原订单id`来查询预支付单
### 请求地址
> http(s)://api.huishouyin.cn/rorder/get

### 请求方式
`GET`
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
|r_no|String|是|64|预付单号|
|order_id|String|是|128|原支付业务单号|
|create_time|Date|是|1|订单创建时间 `2014-11-27 15:45:57`|
|update_time|Date|是|1|最后更新时间 `2014-11-27 15:45:57`|
|total_amount|double|是|-|订单总金额|
|store_info|object|否| - |店铺信息预留域|
|goods_list|Array|否||商品列表|

##### store_info 结构
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|store_id|String|否| - |门店id|
|cashier_id|String|否| - |收银员id|
|waiter1_id|String|否| - |业务员1id|
|waiter2_id|String|否| - |业务员2id|
|terminal_id|String|否| - |终端id|

##### goods_list 结构
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|barcode|String|否|32|国际条码|
|title|String|否|256|商品名称|
|num|int|否|32|商品数量|
|price|double|否| - |单价签名|
### 响应事例
```javascript
{
    code:1000,
    msg:'查询成功',
    data:{
        r_no:'2017102100151091',
        order_id:'2017102100151091',
        app_id:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
        create_time:'2014-11-27 15:45:57',
        update_time:'2014-11-27 15:45:57',
        total_amount:1, 
        store_info:{
            store_id:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
            cashier_id:'5CDJVuPZ89l8hANqsJiU8zWDQ9rUATmg',
            waiter1_id:'HUpLsX7XQWFH3iktwFFMmi1GNdKH7Ef3',
            waiter2_id:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
            terminal_id:'bT2CAkZUgoOr36BnZhuC1aTvXgxhvmhF',
        },
        goods_list:[
            {
                barcode:'6983748939221',
                title:'可口可乐300ml',
                num:2,
                price:3.00
            },{
                barcode:'6987483920018',
                title:'康师傅big香辣牛肉面',
                num:1,
                price:5.00
            }
        ]
    }
}
```
### 异常响应
|名称|描述|
|-----|-----|
|`4003`|预支付单不存在|
### 异常响应事例
```javascript
{
    code:4003,
    msg:'预支付单不存在',
    data:{
        
    }
}
```