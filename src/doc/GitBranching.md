# Git 分支
## 管理或操作模式
+ merge操作 保留痕迹
+ rebase操作 主干干净  
总的原则就是，只对尚未推送或分享给其他人的本地修改执行变基操作清理历史，从不对已经推送到仓库的提交记录执行变基操作；<br />
另一原则，即控制分支数目，小批量频繁集成。

### TBD
一条主干分支走到底

### Git-Flow
主干 master分支
集成 develop分支 开发测试 无问题合并到master  
开发 feature分支 工作隔离 完成后合并到dev  
发布 release分支 发布隔离  
bug hotfix分支 修复 合并到dev和master  
feature/release/hotfix 均为临时分支，需要时从dev或master创建，完成合并后删除。打tag

### GitHub-Flow
pull-request
bug、hotfix、新功能 从master拉分支
新代码完成提交pr 测试审查之后合并到master
从master部署

### GitLab-Flow

## 分支简介
Git 的分支，其实本质上仅仅是指向提交对象的可变指针。  
*Git 的 master 分支并不是一个特殊分支。 它就跟其它分支完全没有区别。git init默认创建*  
*如 remote/origin 也无特殊含义 git clone默认*

### 相关命令
```
git branch <xxx> <commitID>      // (基于某一个commit)创建新分支
git push origin xxx // 推送本地分支到远程仓库 // 关联远程分支-u 或 --set-upstream
git branch          // 查看本地分支
git branch -a       // 查看远程分支
git branch -v       // 查看各分支最新一次提交 -v或-vv
git branch -d xxx   // 删除分支
git branch -m <branchName> newName // 重命名分支

git checkout -b xxx // 新建分支并切换到xxx => git branch xxx + git checkout xxx

git merge hotfix
git branch -d hotfix

git branch --merged
git branch --no-merged // 包含未合并工作的分支
```
*其他*  
`git ls-remote origin`
```
// 切换分支（远程的分支添加到本地）
git checkout -b develop origin/develop
git checkout --track origin/develop
git checkout develop
// 删除远程分支
git push origin -d dev
```