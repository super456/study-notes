# 1.升级node
window和mas系统只能去官网下载最新版本覆盖原来的安装路径即可。

# 2.npm命令操作
- 查看当前npm版本：`npm -v`
- 升级当前npm版本：`npm i npm`
- 罗列出已安装npm模块：`npm list`
- 显示指定模块详情：`npm show express`
- 升级当前目录下的所有模块：`npm update`
- 升级当前目录下的指定模块：`npm update express`
- 升级全局安装的指定模块：`npm update -g express`
- 删除指定模块：`npm uninstall express`

- 检查模块是否过时：`npm outdated`
- 查看模块版本：`npm version`

- 初始化一个基于node的项目，会创建一个配置文件package.json（两种方式）
```
//1.一般情况下 一路enter
 $ npm init

 //2.全部使用默认配置
 $npm init --yes
```

- `--save`和`--save-dev`可以省掉你手动修改package.json文件的步骤。`--save-dev` 是你开发时候依赖的东西，`--save` 是你发布之后还依赖的东西。
`npm install module-name --save `自动把模块和版本号添加到dependencies部分
`npm install module-name --save-dve `自动把模块和版本号添加到devdependencies部分