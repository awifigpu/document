#  什么是restful
简单的说：RESTful是一种架构的规范与约束、原则，符合这种规范的架构就是RESTful架构。
 先看REST是什么意思，英文Representational state transfer 表述性状态转移 其实就是对 资源 的表述性状态转移。
什么是表述性：就是指客户端请求一个资源，服务器拿到的这个资源，就是表述）
资源的地址 在web中就是URL （统一资源标识符）
资源是REST系统的核心概念。**所有的设计都是以资源为中心**

# 为什么要用restful
1.  最早网页都是前端后端融在一起的，比如之前的PHP，JSP等。在之前的桌面时代问题不大，但是近年来移动互联网的发展，各种类型的Client层出不穷，RESTful可以通过一套统一的接口为 Web，iOS和Android提供服务。另外对于广大平台来说，比如Facebook platform，微博开放平台，微信公共平台等，它们不需要有显式的前端，只需要一套提供服务的接口，于是RESTful更是它们最好的选择。
2.  看url就知道要什么。
3. 看http method就知道干什么。

# 特征
1. 每一个uri代表一种资源；
2. 客户端和服务器之间，传递这种资源的某种表现层；
3. 客户端通过四个HTTP动词(GET、POST、DELETE、PUT)，对服务器端资源进行操作，实现"表现层状态转化"(增删改查)。
4. URL中通常不出现动词，只有名词
5. 使用JSON不使用XML

# 设计方式
* HEAD（SELECT）只获取某个资源的头部信息
* GET（SELECT）获取资源
* POST（CREATE）创建资源
* PATCH（UPDATE）更新资源的部分属性（很少用，一般用POST代替）
* PUT（UPDATE）更新资源，客户端需要提供新建资源的所有属性
* DELETE（DELETE）删除资源

# 使用方式
* GET http://address/api/user # 获取列表
* POST http://address/api/user # 创建用户
PUT http://address/api/user/{id} # 修改用户信息
DELETE http://address/api/user/{id} # 删除用户信息

# 过滤信息(我们公司的规范是json)
用于补充规范一些通用字段
?limit=10 # 指定返回记录的数量
?offset=10 # 指定返回记录的开始位置
?page=2&per_page=100 # 指定第几页，以及每页的记录数
?sortby=name&order=asc # 指定返回结果按照哪个属性排序，以及排序顺序
?state=close # 指定筛选条件

# 状态码
字段名称为：code
* 200 OK [GET] 服务器成功返回用户请求的数据，该操作是幂等的（Idempotent）
* 201 CREATED [POST/PUT/PATCH] 用户新建或修改数据成功
* 202 ACCEPTED [*] 表示一个请求已经进入后台排队（异步任务）
* 204 NO CONTENT [DELETE] 用户删除数据成功
* 400 INVALID REQUEST [POST/PUT/PATCH] 用户发出的请求有错误，服务器没有进行新建或修改数据的操作，该操作是幂等的
* 401 UNAUTHORIZED [*] 表示用户没有权限（令牌、用户名、密码错误）
* 403 FORBIDDEN [*] 表示用户得到授权（与401错误相对），但是访问是被禁止的
* 404 NOT FOUND [*] 用户发出的请求针对的是不存在的记录，服务器没有进行操作，该操作是幂等的
* 406 NOT ACCEPTABLE [GET] 用户请求的格式不可得（比如用户请求JSON格式，但是只有XML格式）
* 410 GONE [GET] 用户请求的资源被永久删除，且不会再得到的
* 422 UNPROCESABLE ENTITY [POST/PUT/PATCH] 当创建一个对象时，发生一个验证错误
* 500 INTERNAL SERVER ERROR [*] 服务器发生错误，用户将无法判断发出的请求是否成功

