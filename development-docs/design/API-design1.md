# API设计文档
## 获取主页信息接口
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
'icon': '/static/images/store_img/...',
'storeName': '海底捞火锅',
'starRating': '4',
'price': '150',
'monthlySell': '999',
'distance': '100',
'isDiscount': 'true',
'DiscountNumber': '9',
'isAppOffer' :'false' 
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

## 注册接口
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
'status_code':'201', 'user':{user info}
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
返回错误样例

```
{
'status_code':'401','error_message':'Unauthorized'
}
```
## 登录接口
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
'status_code':'201', 'user':{user info}
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
返回错误样例

```
{
'status_code':'401','error_message':'Unauthorized'
}
```
## 获取店铺点单信息
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
正确结果`foodData.json`：

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
                "icon": "require('./img/restaurant/yuanyangguodi.jpeg')"
            },
            {
                "name":"B锅底",
                "monthlySale":128,
                "like":38,
                "price":38,
                "icon": "require('./img/restaurant/blank.png')"
            },
            {
                "name":"C锅底",
                "monthlySale":128,
                "like":38,
                "price":38,
                "icon": "require('./img/restaurant/blank.png')"
            },
            {
                "name":"D锅底",
                "monthlySale":128,
                "like":38,
                "price":38,
                "icon": "require('./img/restaurant/blank.png')"
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
    <td>picon</td>
    <td>餐品图片链接</td>
  </tr>
</table>  
返回错误样例

```
{
'status_code':'404','error_message':'404 Not Found'
}
```