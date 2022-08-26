# wwkk
Jason's project

## 1 commitlint
#### 安装
`npm install -g @commitlint/cli @commitlint/config-conventional`
#### 生成commitlint.config.js 配置文件
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
- - -

## 2 husky
* husky 是一个增强的 git hook 工具，可以在 git hook 的各个阶段执行我们在 package.json 中配置好的 npm script。
* 借助husky在每次 commit 时执行 commitlint来检查我们输入的 message。
#### 安装
`npm install husky -g`
#### 在package.json中配置
见"husky"
- - -

## 3 commitizen
`npm install commitizen [-D] [-g]`
`npm install cz-conventional-changelog [-D] [-g]`
##### 在package.json中配置
见config -- commitizen
~~是否必须配置待确定！~~
- - -

## 4 changelog
* conventional-changelog-cli生成changelog
* 从git metadata生成变更日志。
#### 安装
`npm install conventional-changelog-cli [-D]`
#### 用法
根目录下新建 CHANGELOG.md<br/>在package.json scripts中添加指令
+ 生成日志
  - "conventional-changelog -p angular -i CHANGELOG.md -s"
+ 包含之前的变更
  - "conventional-changelog -p angular -i CHANGELOG.md -s -r 0"

**在CHANGELOG.md文件中会添加 commit (short)信息**
- - -
* * *
# git操作
#### 创建tag
`git tag <tagName>`  
*以某一次特定推送提交tag*\
`git tag -a <tagName> <commitID>`
#### 推送tag
`git push origin <tagName>`  
*有很多未推送的tag，全部推送*\
`git push origin --tags`

## release和tag管理
* release 可以简单理解为分支(branch)概念
* tag 仅为一个标记
#### 关系
* release 即分支可以基于某一个tag创建，git log查询创建的tag对应的commit  
`git checkout <commitID>`
`git branch <release/xxx>`
##### 如 git branch release/1.0.0
在新建release分支上可以进行基于当前版本的修改，新增tag等操作<br />
可以多种方式将代码合并到master，如 git merge、pr、git cherry-pick 等<br />
