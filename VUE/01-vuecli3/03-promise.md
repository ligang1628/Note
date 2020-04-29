# 1、基本使用
``` 链式编程
new Promise((resolve,reject) => {
	setTimeout(() => {
		resolve()
	})
	// 失败的时候调用
	reject("message")
}).then(() => {
	// 第一次处理的异步代码
	...
	return new Promise((resolve,reject) => {
		setTimeout(() => {
			resolve()
		})
	}).then(() => {
		// 第二次处理的异步代码
		...
		return new Promise((resolve,reject) => {
			setTimeout(() => {
				resolve()
			})
		}).then(() => {
			// 第三次处理的异步代码
		})
	})
}).catch((err) => {
	console.log(err)
})
```
> 第二种写法
```
new Promise((resolve,reject) => {
	setTimeout(() => {
		
	})
}).then(data => {
	
},err => {
	
})
```

# 2、状态
> pending: 等待状态，比如正在请求的时候
> fulfill: 满足状态，当我们主动回调了 resolve 时,就处于该状态，并且会回调 .then()
> reject: 拒绝状态，当我们主动回调了 reject 时，就处于该状态，并且会回调 .catch()

# 3、链式调用

# 4、Promise的all调用
```
Promise.all([
	new Promise((resolve,reject) => {
		$.ajax({
			
		})
	}),
	new Promise((resolve,reject) => {
		$.ajax({
			
		})
	})
]).then(results => {
	// 第一个异步结果 results[0]
	// 第二个异步结果 results[1]
})
```