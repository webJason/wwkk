# Git 基础
## 获取git仓库
#### 初始化仓库
`git init // .git`
#### 克隆现有仓库
`git clone git@github.com:webJason/wwkk.git`
## 检查跟踪
```
git status
git status -s
git add
```
*忽略*
`cat .gitignore`  
*跟踪*
```
git mv xx.md xx.txt // =>相当于
git rm xx.md
git add xx.txt
```
*取消暂存、撤销修改*
```
git reset HEAD <file>... // 参数如--hard、--soft
git reset HEAD -- . // 撤销所有暂存
git reset HEAD xx.js // 从暂存区撤销

git checkout -- <file> // 撤销修改

删除
git rm --cached filename 删除指针
git rm -f filename 删除文件
```
## 提交更新 
```
git commit -m 'xxx'
git commit --amend // 修改commit信息
```
## 查看提交历史
```
git log
git log --oneline --decorate --graph --all
// --stat、--decorate // 简短统计
```
## 远程仓库
```
git remote -v
git remote show origin
git remote rm webJason
git remote add webJason git@github.com:webJason
git remote rename webJason jw // 重命名webJason => jw
```
```
git fetch <remote>
git merge
git pull
git push origin master
```
## 其他
*别名*
`git config --global alias.lg  'log --graph --oneline'`
*查看git操作历史 - 回到某一次操作*
`git reflog`
`git reset --hard id 或者 git reset --hard HEAD@{2}`
