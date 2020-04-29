# history.back()
# history.go()
# hisgory.replaceState
# history.pushState

# 1、vue-router 安装
```
npm install vue-router --save
```
# 2、通过 Vue.use(插件),安装插件
# 3、Vue.use(VueRouter)

# 4、Router-link 属性
> to="/home" 跳转页面
> tag="button" 将router-link 渲染成某个按钮
> replace 无法返回
> active-class="active" 更改类样式名称 可简写
> 在route文件夹下的index.js中新增属性 linkActiveClass:'active'

# 5、通过代码跳转
```
this.$router.push('/home')
// 无法返回
this.$route.replace('/home')
```

# 6、动态路由
> 获取参数
```
{
	path: '/user/:userId',
	name: 'User',
	component: User
}
this.$route.params.[userId]
```

# 7、路由的懒加载

# 8、嵌套路由

# 9、vue-router-keep-alive 保持活跃状态
> 使用方式
```
<keep-alive>
	<router-view/>
</keep-alive>
```
> 使用 keep-alive 时,才可以使用 activated,deactivated
> 属性 include,exclude
> include 字符串或正则表达式，只有匹配的组件会被缓存
> exclude 字符串或正则表达式，任何匹配的组件都不会被缓存
```
<keep-alive inclue="" exclude="">
	<router-view/>
</keep-alive>
```