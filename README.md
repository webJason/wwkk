# wwkk
Jason's project

# 安装
npm install -g @commitlint/cli @commitlint/config-conventional
# 生成commitlint.config.js 配置文件
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js


# husky 是一个增强的 git hook 工具，可以在 git hook 的各个阶段执行我们在 package.json 中配置好的 npm script。
## 借助husky在每次 commit 时执行 commitlint来检查我们输入的 message。
# 安装
npm install husky -g
# 在package.json中配置
见"husky"

# commitizen
npm install commitizen [-D] [-g]
npm install cz-conventional-changelog [-D] [-g]
# 在package.json中配置
见config -- commitizen
# TODO
是否必须配置待确定！
