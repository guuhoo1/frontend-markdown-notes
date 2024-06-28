# git日常常用命令

> 克隆仓库


`git clone https://github.com/xxxx/xxxx.git`

> 关联仓库


`git remote add origin https://github.com/xxxx/xxxx.git`


> 提交

```
git add . // 添加缓存区域
git commit -m "xxx" // 提交信息
git push origin master // 提交到远程仓库
```


> 拉取远程仓库

`git pull origin master`

> 创建分支

`git branch xxx`


> 切换分支

`git checkout xxx`

> 删除分支

`git branch -d xxx`

> 创建远程分支

`git push origin xxx`

> 删除远程分支

`git push origin --delete xxx`


> 创建远程仓库

`git remote add origin https://github.com/xxx/xxx.git`

> 删除远程仓库

`git remote rm origin`


> 合并分支

`git merge xxx`

> 创建标签

`git tag xxx`


