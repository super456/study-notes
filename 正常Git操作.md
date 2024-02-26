## 命令行指令[参考资料git-book]

### （一）开始设置
- Git 全局设置：用户名邮箱设置
```
git config --global user.name "xxx"
git config --global user.email "xxx@xx.com"
```


- 命令来列出所有 Git 当时能找到的配置
`git config --list `

通过输入` git config <key>`： 来检查 Git 的某一项配置如: `git config user.name`

- Git 命令的使用手册(获取帮助)：
```
 git help <verb>
 git <verb> --help
 man git-<verb>
```

如：` git help config`

### （二）创建及使用仓库

- 创建新版本库（克隆现有仓库）
```
git clone git@xxx/xxx.git
cd blockchain
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master
```

添加证书文件：`git add LICENSE`

- 已存在的文件夹或 Git 仓库（现有目录中初始化仓库）
```
cd existing_folder
git init
git remote add origin git@xxx/xxx.git
git add .
git commit
git push -u origin master
```

- 检查当前文件状态：`git status`

- 忽略文件[扩展匹配及详解]

- 查看已暂存和未暂存的修改：

`git diff`:工作目录中当前文件和暂存区域快照之间的差异， 也就是修改之后还没有暂存起来的变化内容。

`git diff --staged`:查看已暂存的将要添加到下次提交里的内容

`git commit -a -m 'added new benchmarks'`:自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 git add 步骤

- 移除文件:从已跟踪文件清单中移除（确切地说，是从暂存区域移除），然后提交
`git rm `

如果删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项 -f（译注：即 force 的首字母）

- 移动文件：`git mv file_from file_to`(重命名文件)

- 查看提交历史：`git log`
一个常用的选项是 -p，用来显示每次提交的内容差异。 你也可以加上 -2 来仅显示最近两次提交：
如果你想看到每次提交的简略的统计信息，你可以使用 --stat 选项：

`git log --pretty=oneline`将每个提交放在一行显示，查看的提交数很大时非常有用

 --graph 结合使用时尤其有用。 这个选项添加了一些ASCII字符串来形象地展示你的分支、合并历史：


 - 撤销对文件的修改
`git reset HEAD CONTRIBUTING.md`:撤销暂存区指定文件
`git checkout -- CONTRIBUTING.md`：撤销对文件的修改

- 查看远程仓库名字：`git remote -v`

- 添加新的远程仓库：`git remote add pb https://github.com/xxx`

`git fetch pb`拉取远程仓库

`git fetch [remote-name]`

`git pull` 通常会从最初克隆的服务器上抓取数据并自动尝试合并到当前所在的分支。

- 推送到远程仓库：`git push [remote-name] [branch-name]`

- 查看远程仓库：`git remote show [remote-name]`

- 远程仓库重命名：`git remote rename pb paul`

- 查看标签：`git tag`

- 创建标签：`git tag -a v1.4 -m 'my version 1.4'`
`git show `命令可以看到标签信息与对应的提交信息

- 共享标签：`git push origin [tagname], git push origin --tags`

- 检出标签：`git checkout -b [branchname] [tagname]` 在特定的标签上创建一个新分支：

- git别名：`git config --global alias.ci commit` => `git ci`

### （三）创建及使用分支

- 创建分支：`git branch testing`

- 查询当前分支情况：`git log --oneline --decorate`

- 切换分支：`git checkout testing`

- 分支历史：`git log --oneline --decorate --graph --all `

- 想要新建一个分支并同时切换到那个分支上，你可以运行一个带有 -b 参数的 git checkout 命令`git checkout -b iss53`

- 合并分支：
 ```
 git checkout master
 git merge hotfix
 ```

 - 解决合并冲突
 ```
 git merge tool
 ```

 - 查看分支
 `git branch`

 - 如果需要查看每一个分支的最后一次提交，可以运行` git branch -v `命令
 --merged 与 --no-merged 这两个有用的选项可以过滤这个列表中已经合并或尚未合并到当前分支的分支。

 - 删除分支：`git branch -d hotfix`

[参考资料git-book]:https://git-scm.com/book/zh/v2
[扩展匹配及详解]:https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93
