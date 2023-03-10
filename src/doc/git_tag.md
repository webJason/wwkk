# git tag 使用文档
指向某一次commit(id) 对某一次提交或分支进行标记
### 基本用法
+ 创建tag  
  `git tag <xx>`  
  `git tag -a <xx> -m <注释> // 创建带注释的tag`  
  `git tag -a <xx> <commitID> // 基于某一次commit创建tag`
  - 场景：
  - 1 标记 版本、分支
  - 2 追加标签
+ 查看tag  
  `git tag // 查看本地tag`  
  `git ls-remote --tags origin // 查看远程所有tag`  
  `git show <tag> // 查看tag详细信息`
+ 提交tag  
  `git push origin <xx>`  
  `git push origin --tags // 推送本地所有tag`
+ 删除tag  
  `git tag -d <xx> // 删除本地tag`  
  `git push origin :<tag> // 删除远程tag`
  `git push origin -d <tag> // 删除远程tag`
  - 场景：
  - 1 发版后发现问题，产生新的commit，删除后重新标记
### 其他用法
+ 有序显示最后一次tag及之前commit  
  `git rev-list --tags`