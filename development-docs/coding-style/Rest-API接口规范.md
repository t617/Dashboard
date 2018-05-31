
### 一、协议
API与用户的通信协议，总是使用HTTPs协议。

### 二、域名
尽量将API部署在专用域名之下。
如：
>https://api.example.com

### 三、版本
如果更新迭代涉及到了API版本的更新  
则将版本号放在HTTP头信息中

### 四、URI规范
1.不用大写  
2.单词间用下划线_  
3.参数列表要encode  
4.URI中的名词表示资源集合，使用复数形式。如：如：user、rooms、food_lists  

### 五、请求Request
* GET（SELECT）：从服务器取出资源（一项或多项）。
* POST（CREATE）：在服务器新建一个资源。
* PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。
* PATCH（UPDATE）：在服务器更新资源（客户端提供改变的属性）。
* DELETE（DELETE）：从服务器删除资源。

例子：

* GET /zoos：列出所有动物园
* POST /zoos：新建一个动物园
* GET /zoos/ID：获取某个指定动物园的信息
* PUT /zoos/ID：更新某个指定动物园的信息（提供该动物园的全部信息）
* PATCH /zoos/ID：更新某个指定动物园的信息（提供该动物园的部分信息）
* DELETE /zoos/ID：删除某个动物园
* GET /zoos/ID/animals：列出某个指定动物园的所有动物
* DELETE /zoos/ID/animals/ID：删除某个指定动物园的指定动物

### 六、过滤信息Filtering
如果记录数量很多，服务器不可能都将它们返回给用户。API应该提供参数，过滤返回结果。  
常见的参数：
* ?limit=10：指定返回记录的数量
* ?offset=10：指定返回记录的开始位置。
* ?page=2&per_page=100：指定第几页，以及每页的记录数。
* ?sortby=name&order=asc：指定返回结果按照哪个属性排序，以及排序顺序。
* ?animal_type_id=1：指定筛选条件

### 七、状态码
**成功：**
* 200 OK - [*]:请求成功并返回实体资源
* 201 CREATED - [POST]:创建资源成功

**客户端错误：**
* 400 INVALID REQUEST - [POST/PUT/PATCH]:用户发出的请求有错误，一般是参数错误
* 401 Unauthorized - [*]:一般用户验证失败（用户名、密码错误等）
* 403 Forbidden - [*]:一般用户权限校验失败
* 404 Not Found - [*]:资源不存在

**服务器错误：**
* 500 INTERNAL SERVER ERROR - [*]:服务器发生错误

### 八、返回结果
针对不同操作，服务器向用户返回的结果应该符合以下规范。
* GET /collection：返回资源对象的列表（数组）
* GET /collection/resource：返回单个资源对象
* POST /collection：返回新生成的资源对象
* PUT /collection/resource：返回完整的资源对象
* PATCH /collection/resource：返回完整的资源对象
* DELETE /collection/resource：返回一个空文档

### 九、其他
（1）服务器返回的数据格式，应该尽量使用JSON，避免使用XML。

