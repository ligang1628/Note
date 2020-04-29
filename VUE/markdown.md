# 实现 markdown 编辑器
* 安装 `npm install mavon-editor --save`
* 扩展表情 `npm install markdown-it-emoji --save`
* 修改 webpack 版本(4.0.0/5.0.0) `npm install webpack@4.0.0 -g`
* 获取编译后的 html
* `this.$refs.editor.d_render`
* 获取 markdown
* `this.$refs.editor.d_value`

# 同步远程信息
* 从远程获取最新版本到本地 `git fetch origin master`
* 比较远程仓库和本地仓库的区别 `git log -p master.. origin/master`
* 将远程下载下来的最新代码合并到本地仓库，远程的和本地合并 `git merge origin/master`

# elementui
## Cascader 级联选择器
* 获取最后一个节点的值 `this.$refs.Category.getCheckedNodes()[0].value`