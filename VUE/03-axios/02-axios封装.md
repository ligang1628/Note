import axios from 'axios'

> 方式一
```
export function request(config, success, failure) {
	const instance = axios.create({
		baseUrl:'',
		timeout:5000
	})
	
	// 发送真正的网络请求
	instance(config).then(res => {
		success(res)
	}).catch(err => {
		failure(err)
	})
	
}
```
> 方式二
```
export function request(config) {
	const instance = axios.create({
		baseUrl:'',
		timeout:5000
	})
	
	// 发送真正的网络请求
	instance(config.baseConfig).then(res => {
		config.success(res)
	}).catch(err => {
		config.failure(err)
	})
	
}
```
> 方式三
```
export function request(config) {
	return new Promise((resolve,reject) => {
		const instance = axios.create({
			baseUrl:'',
			timeout:5000
		})
		
		// 拦截器
		instance.interceptors.request.use(config => {
			config.headers={'x-Requested-With':'XMLHttpRequest'}
			return config
		}, err => {
			return err
		})
		
		// 响应拦截
		instance.interceptors.response.use(res => {
			return res.data
		}, err => {
			return err
		})
		
		// 发送真正的网络请求
		return instance(config.baseConfig)
	})
	
}
```