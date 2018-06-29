### API设计文档
### 1.获取主页信息接口
**应用场景**  
APP端调起店铺信息参数  
**接口链接**  
无  
**是否需要证书**  
否  
**请求说明**  
http请求方式: GET  
**返回说明**   
返回结果：

```
{
'icon': '',
'storeName': '',
'starRating': '',
'price': '',
'monthlySell': '',
'distance': '',
'isDiscount': '',
'DiscountNumber': '',
'isAppOffer' :'' 
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>icon</td>
    <td>店铺图片地址</td>
  </tr>
  <tr>
    <td>storeName</td>
    <td>店铺名称</td>
  </tr>
  <tr>
    <td>starRating</td>
    <td>店铺评分</td>
  </tr>
  <tr>
    <td>price</td>
    <td>菜品价格</td>
  </tr>
  <tr>
    <td>monthlySell</td>
    <td>店铺月销量</td>
  </tr>
  <tr>
    <td>distance</td>
    <td>店铺距离</td>
  </tr>
  <tr>
    <td>isDiscount</td>
    <td>是否打折</td>
  </tr>
  <tr>
    <td>DiscountNumber</td>
    <td>折扣信息</td>
  </tr>
  <tr>
    <td>isAppOffer</td>
    <td>是否APP专享优惠</td>
  </tr>
</table>  

### 2.注册接口
**应用场景**  
APP端用户进行注册  
**接口链接**  
无  
**是否需要证书**  
否  
**请求说明**  
http请求方式: GET、POST  
**参数说明**  
<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>phone_num</td>
    <td>用户注册手机号</td>
  </tr>
  <tr>
    <td>password</td>
    <td>用户注册密码</td>
  </tr>
</table> 
**返回说明**   
正确结果：

```
{
'status_code':'', 
"user": {
    "ID": '',
    "username": '',
    "name": '',
    "avar": '',
    "message": '',
    "orderList": []
}
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>status_code</td>
    <td>状态码</td>
  </tr>
  <tr>
    <td>user</td>
    <td>注册成功资源实体</td>
  </tr>
</table> 


<table border="1">
 <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> ID </td>
    <td>用户id</td>
  </tr>
  <tr>
    <td> username </td>
    <td>用户手机号</td>
  </tr>
  <tr>
    <td> name </td>
    <td>用户昵称</td>
  </tr>
  <tr>
    <td> avar </td>
    <td>用户头像</td>
  </tr>
  </tr>
    <tr>
    <td> message </td>
    <td>用户描述</td>
  </tr>
  <tr>
    <td> orderList </td>
    <td>点餐信息</td>
  </tr>
</table> 
 
返回错误样例

```
{
'status_code':'401','error_message':'Unauthorized'
}
```

### 3.登录接口
**应用场景**  
APP端用户进行登录  
**接口链接**  
无  
**是否需要证书**  
否  
**请求说明**  
http请求方式: GET、POST  
**参数说明**  

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>phone_num</td>
    <td>用户注册手机号</td>
  </tr>
  <tr>
    <td>password</td>
    <td>用户注册密码</td>
  </tr>
</table> 

**返回说明**   
正确结果：

```
{
'status_code':'201', 
"user": {
    "ID": '',
    "username": '',
    "name": '',
    "avar": '',
    "message": '',
    "orderList": []
}
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>status_code</td>
    <td>状态码</td>
  </tr>
  <tr>
    <td>user</td>
    <td>登录成功资源实体</td>
  </tr>
</table> 


<table border="1">
 <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> ID </td>
    <td>用户id</td>
  </tr>
  <tr>
    <td> username </td>
    <td>用户手机号</td>
  </tr>
  <tr>
    <td> name </td>
    <td>用户昵称</td>
  </tr>
  <tr>
    <td> avar </td>
    <td>用户头像</td>
  </tr>
  </tr>
    <tr>
    <td> message </td>
    <td>用户描述</td>
  </tr>
  <tr>
    <td> orderList </td>
    <td>点餐信息</td>
  </tr>
</table>

orderList参数：orderlist是由多个Order_detail组成的数据

```
Order_detail = {
    'orderID' = '',
    'storeName' = '',
    'rating' = '',
    'date' = '',
    'cost' = ''
}
```


<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> orderID </td>
    <td>订单号</td>
  </tr>
  <tr>
    <td> storeName </td>
    <td>店铺名称</td>
  </tr>
  <tr>
    <td>rating </td>
    <td>评分</td>
  </tr>
  <tr>
    <td>date </td>
    <td>日期</td>
   </tr>
   <tr>
    <td>cost </td>
    <td>花费</td>
   </tr>
</table> 
 
返回错误样例

```
{
'status_code':'401','error_message':'Unauthorized'
}
```

### 4.获取店铺菜品信息
**应用场景**  
APP端用户点进单个店铺后获取的信息  
**接口链接**    
  host/index/store_name  
**是否需要证书**    
否  
**请求说明**  
http请求方式: GET  
**参数说明**  
无  
**返回说明**   
正确结果：

```
{
    "foodData":[
    {
        "title": "锅底",
        "id": 1,
        "data":[
            {
                "name":"鸳鸯锅底",
                "monthlySale":1228,
                "like":329,
                "price":38,
                "icon": "require('')"
            },
            {
                "name":"B锅底",
                "monthlySale":128,
                "like":38,
                "price":38,
                "icon": "require('')"
            },
            {
                "name":"C锅底",
                "monthlySale":128,
                "like":38,
                "price":38,
                "icon": "require('')"
            },
            {
                "name":"D锅底",
                "monthlySale":128,
                "like":38,
                "price":38,
                "icon": "require('')"
            }
        ]
    },
    ...
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>title</td>
    <td>餐品类型</td>
  </tr>
  <tr>
    <td>name</td>
    <td>餐品可选种类</td>
  </tr>
      <tr>
    <td>like</td>
    <td>点赞数</td>
  </tr>
    <tr>
    <td>monthlySale</td>
    <td>餐品月销量</td>
  </tr>
  <tr>
    <td>price</td>
    <td>餐品价格</td>
  </tr>
    <tr>
    <td>icon</td>
    <td>餐品图片链接</td>
  </tr>
</table> 
 
返回错误样例

```
{
'status_code':'404','error_message':'404 Not Found'
}
```

### 5.获取订单详情接口
**应用场景**  
APP端调起订单信息参数   
**接口链接**    
无  
**是否需要证书**    
否  
**请求说明**  
http请求方式: GET  
**参数说明**  

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>userID</td>
    <td>用户ID</td>
  </tr>
  <tr>
    <td>orderID</td>
    <td>用户订单号</td>
  </tr>
</table>  
 
**返回说明**   
返回结果：  

```
order_detail = {
    'status_code': '',
    'storeName': '',
    'foodList': '',
    'mealFee': '',
    'ServiceFee': '',
    'totalFee': '',
    'Offer': '',
    'paymentMethod': '',
    'Date': '',
    'orderNumber': ''
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> status_code </td>
    <td>状态码</td>
  </tr>
  <tr>
    <td> storeName </td>
    <td>店铺名称</td>
  </tr>
      <tr>
    <td> foodList </td>
    <td>食物列表，格式下面给出</td>
  </tr>
    <tr>
    <td> mealFee </td>
    <td>餐费</td>
  </tr>
  <tr>
    <td> ServiceFee </td>
    <td>服务费</td>
  </tr>
    <tr>
    <td> totalFee </td>
    <td>总费用</td>
  </tr>
  </tr>
    <tr>
    <td> paymentMethod </td>
    <td>支付方式</td>
  </tr>
  </tr>
    <tr>
    <td> Offer </td>
    <td>是否打折</td>
  </tr>
  </tr>
    <tr>
    <td> Date </td>
    <td>点餐日期</td>
  </tr>
  </tr>
    <tr>
    <td> orderNumber </td>
    <td>订单号(unique)</td>
  </tr>
</table> 

foodList参数：foodlist是由多个Food_detail组成的数据

```
Food_detail = {
    "dishName": '',
    "price": '',
    "number": ''
}
```


<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> dishName </td>
    <td>食品名称</td>
  </tr>
  <tr>
    <td> price </td>
    <td>食品价格</td>
  </tr>
      <tr>
    <td> number </td>
    <td>食品数目</td>
</table> 

### 6.店铺分类搜索接口
**应用场景**  
APP端进行店铺搜索参数  
**接口链接**  
无  
**是否需要证书**  
否  
**请求说明**  
http请求方式: GET，POST  
**参数说明**  
 
<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> type </td>
    <td>食品种类</td>
  </tr>
</table> 

**返回说明**   
返回结果：

```
{
'icon': '',
'storeName': '',
‘storeid’: ''
'starRating': '',
'price': '',
'monthlySell': '',
'distance': '',
'isDiscount': '',
'DiscountNumber': '',
'isAppOffer' :'' 
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>icon</td>
    <td>店铺图片地址</td>
  </tr>
  <tr>
    <td>storeName</td>
    <td>店铺名称</td>
  </tr>
  <tr>
    <td>storeid</td>
    <td>店铺id</td>
  </tr>
  <tr>
    <td>starRating</td>
    <td>店铺评分</td>
  </tr>
  <tr>
    <td>price</td>
    <td>菜品价格</td>
  </tr>
  <tr>
    <td>monthlySell</td>
    <td>店铺月销量</td>
  </tr>
  <tr>
    <td>distance</td>
    <td>店铺距离</td>
  </tr>
  <tr>
    <td>isDiscount</td>
    <td>是否打折</td>
  </tr>
  <tr>
    <td>DiscountNumber</td>
    <td>折扣信息</td>
  </tr>
  <tr>
    <td>isAppOffer</td>
    <td>是否APP专享优惠</td>
  </tr>
</table>  

### 7.用户订单详情
**应用场景**  
APP端调起单个用户所用订单信息   
**接口链接**    
无  
**是否需要证书**    
否  
**请求说明**  
http请求方式: GET  
**参数说明**  

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>userID</td>
    <td>用户ID</td>
  </tr>
</table>  

**返回说明**   
返回结果：  

```
order_detail = {
    'status_code': '',
    'storeName': '',
    'OrderList': '',
    'mealFee': '',
    'ServiceFee': '',
    'totalFee': '',
    'Offer': '',
    'paymentMethod': '',
    'Date': '',
    'orderNumber': ''
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> status_code </td>
    <td>状态码</td>
  </tr>
  <tr>
    <td> storeName </td>
    <td>店铺名称</td>
  </tr>
      <tr>
    <td> OrderList </td>
    <td>食物列表，格式下面给出</td>
  </tr>
    <tr>
    <td> mealFee </td>
    <td>餐费</td>
  </tr>
  <tr>
    <td> ServiceFee </td>
    <td>服务费</td>
  </tr>
    <tr>
    <td> totalFee </td>
    <td>总费用</td>
  </tr>
  </tr>
    <tr>
    <td> paymentMethod </td>
    <td>支付方式</td>
  </tr>
  </tr>
    <tr>
    <td> Offer </td>
    <td>是否打折</td>
  </tr>
  </tr>
    <tr>
    <td> Date </td>
    <td>点餐日期</td>
  </tr>
  </tr>
    <tr>
    <td> orderNumber </td>
    <td>订单号(unique)</td>
  </tr>
</table> 

orderList参数：orderlist是由多个Order_detail组成的数据

```
Order_detail = {
    'orderID' = '',
    'storeName' = '',
    'rating' = '',
    'date' = '',
    'cost' = ''
}
```


<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> orderID </td>
    <td>订单号</td>
  </tr>
  <tr>
    <td> storeName </td>
    <td>店铺名称</td>
  </tr>
  <tr>
    <td>rating </td>
    <td>评分</td>
  </tr>
  <tr>
    <td>date </td>
    <td>日期</td>
   </tr>
   <tr>
    <td>cost </td>
    <td>花费</td>
   </tr>
</table> 

### 8.修改个人信息api
**应用场景**  
APP端用户修改个人信息  
**接口链接**    
无  
**是否需要证书**    
否  
**请求说明**  
http请求方式: POST, GET  
**参数说明**  

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td>username</td>
    <td>用户昵称</td>
  </tr>
  <tr>
    <td>phone_number</td>
    <td>用户电话号码</td>
  </tr>
    <tr>
    <td>old_password</td>
    <td>用户旧密码</td>
  </tr>
    <tr>
    <td>new_password</td>
    <td>用户新密码</td>
  </tr>
</table>  
 
**返回说明**   
返回结果：  

```
user_data = {
    'status_code': '',
    'token': '',
    'duration': '',
    "user": {
        "ID": '',
        "username": '',
        "name": '',
        "avar": '',
        "message": '',
        "orderList": []
    }
}
```

<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> status_code </td>
    <td>状态码</td>
  </tr>
  <tr>
    <td> token </td>
    <td>用户token</td>
  </tr>
      <tr>
    <td> duration </td>
    <td>token有效时间</td>
  </tr>
 </table>
 

<table border="1">
 <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> ID </td>
    <td>用户id</td>
  </tr>
  <tr>
    <td> username </td>
    <td>用户手机号</td>
  </tr>
  <tr>
    <td> name </td>
    <td>用户昵称</td>
  </tr>
  <tr>
    <td> avar </td>
    <td>用户头像</td>
  </tr>
  </tr>
    <tr>
    <td> message </td>
    <td>用户描述</td>
  </tr>
  <tr>
    <td> orderList </td>
    <td>点餐信息</td>
  </tr>
</table> 

orderList参数：orderlist是由多个Order_detail组成的数据

```
Order_detail = {
    'orderID' = '',
    'storeName' = '',
    'rating' = '',
    'date' = '',
    'cost' = ''
}
```


<table border="1">
  <tr>
    <th>参数</th>
    <th>说明</th>
  </tr>
  <tr>
    <td> orderID </td>
    <td>订单号</td>
  </tr>
  <tr>
    <td> storeName </td>
    <td>店铺名称</td>
  </tr>
  <tr>
    <td>rating </td>
    <td>评分</td>
  </tr>
  <tr>
    <td>date </td>
    <td>日期</td>
   </tr>
   <tr>
    <td>cost </td>
    <td>花费</td>
   </tr>
</table> 

