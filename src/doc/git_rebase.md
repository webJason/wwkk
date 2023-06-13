## git rebase
`git rebase -i HEAD~5 // 往前第n次commit`

|编号|选项列表|对应含义解释
|:-:|:-|:-|
|1|p/pick	|使用这个 commit 记录
|2|r/reword	|使用这个 commit 记录；并且修改提交信息
|3|e/edit	|使用这个 commit 记录；rebase 时会暂停允许你修改这个 commit
|4|s/squash	|使用这个 commit 记录；会将当前 commit 与上一个 commit 合并
|5|f/fixup	|与 squash 选项相同；但不会保存当前 commit 的提交信息
|6|x/exec	|执行其他 shell 命令
|7|d/drop	|移除这个 commit 记录

### 演示情况
*本地未push 不要合并已提交到仓库的提交*
1. 删除某一次commit
2. 合并多个commit

### 保存操作
1. 编辑完成，按键盘Esc，退出编辑模式，然后按Shift+“:”
2. 再输入wq!（保存文件的写入修改）退出。（q!是不保存修改）。

#### 变基操作
*新feature分支基于master-commit-A，当master提交新commit-N*  
*变基就相当于已master新的提交作为feature分支的**基底***
```
git checkout feature
git rebase master // 将feature基底修改为commit-N
```
```
// =>
git rebase master feature // feature 续到master后面
git rebase feature // 在master执行 将feature提交前置到master新提交前
```
```
// master - server - client
git rebase --onto master server client
// 取出 client 分支，找出它从 server 分支分歧之后的补丁， 然后把这些补丁在 master 分支上重放一遍，
// 让 client 看起来像直接基于 master 修改一样
```
*冲突*
```
解决冲突
git add 冲突文件 // 依次解决
git rebase --continue // 不是git commit

出现(<branch-name>|REBASE */*) 解决方式
git rebase --abort // 中止
```

* 好处 提交记录简洁，不存在分叉（与git merge相比）  
* 缺点 操作后不知道当前分支最早是基于哪个分支
- - -
总的原则是，只对尚未推送或分享给别人的本地修改执行变基操作清理历史， 从不对已推送至别处的提交执行变基操作
- - -
## rebase/revert/reset
**reset**  
reset是彻底回退到指定的commit版本，该commit后的所有commit都将被清除，包括提交历史记录；  
*参数 --soft 保留修改 --hard 不保留修改*  
`git reset --hard <commitID>`  
`git reset --soft HEAD~5`  
**revert**  
revert仅仅是撤销指定commit的修改，并不影响后续的commit，但所撤销的commit被后续的commit修改了同一地方则会产生冲突；  
`git revert <commitID>`
+ reset执行后不会产生记录，revert执行后会产生记录；
+ reset执行后无法再次恢复，revert执行后因为不会清除记录，并且会产生新纪录，所以文件不会丢失，你可以多次执行revert恢复到某次改变之前的状态；
+ reset执行后HEAD会后移，而revert的HEAD则一直是向前的；
