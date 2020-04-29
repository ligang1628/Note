> 说明
> Webpack 在安装vuecli时会自动安装
> 清空npm
> 或者去 C:\Users\Administrator\AppData\Roaming 文件夹下删除 npm-cache文件夹
```
npm clear cache --force
```

# 1、cnpm 安装
* 设置淘宝镜像

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

# 2、webpack 安装
`npm install webpack -g`

# 3、vue安装
> -dev 指开发时依赖
> 在后续的开发过程中会使用vue,不需要使用-dev
> 也可简写 `npm install vue -S`
`npm install vue --save`

* runtime-only 代码中不可以有任何的 template
* runtime-compiler 代码中可以有template,因为有compiler可以用于编译template

```
npm install --save-dev vue-loader@13.0.0 vue-template-compiler
```

## 3.1 打包html的plugin
```
npm install html-webpack-plugin@3.2.0 --save-dev
```

## 3.2 js 压缩的Plugin
```
npm install uglifyjs-webpack-plugin@1.1.1 --save-dev
```

# 4、安装vue脚手架
>全局安装就行
> -g => global(全局)
> 脚手架三

```
npm install -g @vue/cli
```

* Vue Cli3初始化项目

```
vue create my-project
```

> 拉取2.*版本

```
npm install @vue/cli-init -g
```

* Vue Cli2初始化项目

```
vue init webpack my-project
```

# 5、禁用ESLINT
* 在config文件夹下index.js中找到useEslint

# 6、MD5加密
`npm install --save js-md5`
