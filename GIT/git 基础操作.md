>>
个人使用
>>

# 1、检测是否存在密匙
```
cd ~/.ssh
```
* 1.1、若不存在密匙 则显示 `No Such file or directory`
> 解决方案
> 1.1.1 执行 导航2 操作
> 1.1.2 创建密匙 `ssh-keygen -t rsa -C [userEmail]` 回车三次
> 1.1.3 可以去用户主目录 C:\Users\Administrator 找到 .ssh 目录 ，里面有id_rsa 和 id_rsa.pub 两个文件，这两个就是 SSH Key 的密匙对，id_rsa 是私匙，不能泄露出去，id_rsa.pub 是公匙，可以放心的告诉别人

# 2、登录，进行全局配置
```
git config --global user.name 'yourname'
git config --global user.email 'yourEmail'
```

# 3、创建初始库
```
mkdir [fileName]
e.g.: `mkdir note`
```

# 4、将该目录变成git可以管理的仓库
```
git init
```

# 5、查看状态
```
git status
```

# 6、添加
> git add . 添加的是多个文件
> git add note/ 添加的 note 文件夹下的文件
```
git add .
```

# 7、提交
```
git commit -m "tips(提示)"
```

# 8、关联 github 仓库
> 有两种方式
> 第一种
> git remote add origin https://github.com/[username]/[project].git
> 第二种(第一种不生效的情况下)
> git remote add origin https://[username]:[userpwd]@github.com/[username]/[project].git
```
git remote add origin https://github.com/[username]/[project].git
git remote add origin https://[username]:[userpwd]@github.com/[username]/[project].git
```

# 9、查看远程信息
```
1、查看已存在的存储库
git remote -v
2、删除所有已关联的存储库
git remote remote origin
3、关联存储库
git remote add origin [linkAddress]
```

# 10、推送
> 第一次关联仓库进行推送
```
git push origin master
```
> 后续推送
```
git push
```

# 11、克隆
```
git clone git@github.com:[username]/[project].git
```
> 11.1 下载完成后进行仓库目录
```
cd [filename]
```
> 11.2 查看该文件中有哪些文件
```
ls
```
> 11.3 返回上一目录
```
cd .. or cd ~
```
> 11.4 返回根目录
```
cd /
```

# 12、获取最新更新至本地
> 12.1 拉取更新
```
git fetch origin master
```
> 12.2 对比差异
```
git fetch origin master
按 q 退出
```
> 12.2 合并
```
git merge origin master
```

# 13、创建分支
> 13.1 查看分支
```
git branch
```
> 13.2 创建分支
```
git branch [name]
```
> 13.3 切换分支
```
git checkout [name] OR git switch [name]
```
> 13.4 创建+切换分支
```
git checkout -b [name] OR git switch -c [name]
```
> 13.5 删除分支
```
git branch -d [name]
```
> 13.5.1 查看分支合并图
* git log: 显示从最近到最远的提交日志，包括每个提交的 SHA-1 校验和、作者的名字和电子邮件地址、提交时间以及提交说明等基本信息。
* git log --graph: 查看分支合并图
* git log --graph --pretty=oneline --abbrev-commit: 查看分支的合并情况，包括分支合并图、一行显示、提交校验码缩略显示。
* git log --oneline --decorate --graph --all: 查看分叉历史，包括: 提交历史、各个分支的指向以及项目的分支分叉情况。

> 13.5.2 合并某分支到当前分支
* 注意：
* 合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。
* 合并分支时，如果可能，git会使用Fast forward模式，在这种模式下，删除分支后，会丢失掉分支信息，
* 使用--no-ff参数，表示禁用Fast forward
* git merge --no-ff -m "Msg" dev	--准备合并dev分支，使用普通模式合并，因为本次合并要创建一个新的commit，所以加上-m参数，备注Msg
```
git merge [name] / git merge --no-ff -m "Msg" dev	,然后推送 push
```

# 14、撤销分支做的更改
* 新建一个分支dev	 => 
```
git checkout -b dev
```
* 在分支中新建一个文件my.py 	
```
touch my.py
```
* 新增、提交
```
git add my.py & git commit -m "insert branch dev"
```
* 返回上一级分支 
```
git branch master
```
* 删除分支/合并分支	
* 若没有合并，如果删除分支，需要进行强行删除
```
git branch -D dev
```
* 5.2、已合并分支，
* 5.3、合并分支 
```
git merge --no-ff -m "Msg" dev
```
* 推送分支，将所有本地提交推送到远程库，推送时，要指定本地分支
```
git push origin master/分支名
```

# 15、创建标签
> 创建标签
```
git tag tagName
```
> 查看标签
```
git tag
```
> 创建带有说明的标签，-a指定标签名，-m指定说明文字
```
git tag -a tagName -m "version 0.1 released"  02wer（命令）
```
> 删除标签
```
git tag -d tagName
```
> 推送标签到远程
```
git push origin tagName
```
> 一次性推送全部尚未推送到远程的本地标签
```
git push origin -tags
```
> 如果标签一件推送到远程，先删除本地标签再删除远程标签
```
git tag -d tagName
git push origin :refs/tags/tagName
```

合并两个独立启动仓库的历史
git pull origin master --allow-unrelated-histories

git push origin master:master

https://www.cnblogs.com/smiler/p/11576773.html