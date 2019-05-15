# 获取请求的HTTP方法
```
method = request.method
```

# 获取请求头
```
headers = request.headers
```

# 获取url
```
url = request.url
```

# 获取cookies
```
cookies = request.cookies
```

# 获取url  GET参数
```
args = request.args
```

# 获取POST参数
```
args = request.get_data()
# 注:如果是form表单提交的POST数据请使用request.form
```

# 获取POST json参数
```
args = request.get_json()
# 注: get_json()  会自动将json数据转换为字符串,还有POST请求需要设置请求头发送参数为application/json格式,才可以接收到
# 如果没有设置成json格式发送,请使用get_data接收参数
```

# 获取form表单数据
```
form_name = request.form.get("name")
form_age = request.form.get("age")
# get里面的参数由input标签里面的name属性值决定
```

# 获取上传的文件
```
files = request.files.get("image")
#注:get里面的参数,由html form表单里面input的name属性值决定
```

# 代码
[flask 参数](https://github.com/awifigpu/flask_example/tree/1905015)
