# 1、安装
```
npm install axios --save
```

> 属性

```
axios.defaults.baseURL = "http://192.168.132.11:80"
axios.defaults.timeout = 5000
请求地址： url
请求类型：method
请根路径：baseURL
请求前的数据处理：transformRequest:[function(data){}]
请求后的数据处理：transformResonse:[function(data){}]
自定义的请求头：headers:{'x-Requested-With':'XMLHttpRequest'}
URL查询对象：params:{id:2}
查询对象序列化函数：paramsSerializer:function(params){}
请求body：request body data:{key:'aa'}
超时设置：timeout:1000
跨域是否带Token:withCredentials:false
自定义请求处理：adapter:function(resolve,reject,config)
身份验证信息：auth:{uname:'',pwd:'12'}
响应的数据格式：json/blob/document/arraybuffer/text/stream
	e.g.:responseType:'json'
```

```
const instance = axios.create({
	baseURL: "http://12.31.3.4",
	timeout: 5000
})

instance({
	url:'/getcategory'
}).then(res => {
	
})

instance({
	url:'',
	params:{
		id:1
	}
}).then(res => {
	
})
```