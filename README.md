# wwkk
Jason's project

## 1 commitlint
#### 安装
`npm install -g @commitlint/cli @commitlint/config-conventional`
#### 生成commitlint.config.js 配置文件
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
* * *
- - -

## 2 husky
* husky 是一个增强的 git hook 工具，可以在 git hook 的各个阶段执行我们在 package.json 中配置好的 npm script。*
* 借助husky在每次 commit 时执行 commitlint来检查我们输入的 message。*
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
* conventional-changelog-cli生成changelog *
* 从git metadata生成变更日志。*
#### 安装
`npm install conventional-changelog-cli [-D]`
#### 用法
根目录下新建 CHANGELOG.md
在package.json scripts中添加指令
生成日志
"conventional-changelog -p angular -i CHANGELOG.md -s"
包含之前的变更
"conventional-changelog -p angular -i CHANGELOG.md -s -r 0"
***在CHANGELOG.md文件中会添加 commit (short)信息***
- - -
