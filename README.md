# Git 学习

- 初始化仓库：`git init`
- 清空git命令行：`clear`
- 添加文件到暂存区：`git add <filename>`
- 添加全部文件到暂存区：`git add .`
- 查看git状态：`git status`
- 提交文件到git仓库：`git commit -m '信息'`
- 提交已经处于追踪状态下的文件到仓库：`git commit -am '信息'`

- 显示由近到远的提交日志，如果无法退出，可以按q退出：`git log`
- 简易一行显示日志：`git log --pretty=oneline`
- 退回上一版本：`git reset --hard HEAD^`
- 单个文件从暂存区回退到工作区：`git reset HEAD <filename>`
- 退回上上一个版本：`git reset --hard HEAD^^`
- 退回上100个版本：`git reset --hard HEAD~100`
- 退出指定版本：`git reset --hard <commit id>`
- 查看历史命令：`git reflog`

- 查看修改：`git diff <filename>`
- 查看工作区和版本库里面最新版本的区别：`git diff HEAD -- <filename>`
- 丢弃工作区的修改（未进行add）：`git checkout -- <filename>`
- 撤销暂存区的修改（已进行add，未进行commit）：先回退到上一版本 `git reset HEAD <filename>`，再丢弃工作区的修改 `git checkout -- <filename>`
- 删除文件：`git rm <filename>`
- 找回删除的文件（未进行commit）：先执行 `git reset HEAD <filename>`，再执行 `git checkout -- <filename>`
- 找回删除的文件（已进行commit）：回到上一版本 `git reset --hard HEAD^`

- 查看分支：`git branch`
- 创建分支：`git branch <branchname>`
- 切换分支：`git checkout <branchname>`
- 创建并切换到分支：`git checkout -b <branchname>`
- 删除分支：`git branch -d <branchname>`
- 合并分支到当前分支：`git merge <branchname>`

解决分支合并冲突：
- 1、查看分支冲突文件
- 2、手动解决冲突，删除或保留某些文件
- 3、重新执行 `git add` 和 `git commit`
  
- 简易查看分支合并情况：`git log --graph --pretty=oneline --abbrev-commit`
- 详细查看分支合并情况：`git log --graph`

- 存储当前工作现场：`git stash`
- 查看存储的工作现场列表：`git stash list`
- 恢复指定的工作现场：`git stash apply <stashname>`
- 删除指定的stash内容：`git stash drop <stashname>`
- 恢复并删除stash内容：`git stash pop`
- 在master分支上修复的bug，合并到当前dev分支上：`git cherry-pick <commit id>`
- 丢弃一个没有被合并过的分支，强制删除分支：`git branch -D <branchname>`


- 推送分支到远程：`git push origin <branchname>`
- 显示远程仓库信息：`git remote -v`
- 创建远程分支到本地：`git checkout -b <branchname> origin/<branchname>`
- 关联本地分支与远程分支：`git branch --set-upstream-to=origin/<branchname> <branchname>`
- 推送代码失败时：先 `git pull` 拉取最新代码，本地进行合并，解决冲突，再 `git push` 推送

- 查看历史版本提交：`git log --pretty=oneline --abbrev-commit`
- 创建标签：`git tag <tagname>`
- 给历史提交打标签：`git tag <tagname> <commit id>`
- 查看标签信息：`git show <tagname>`
- 查看全部标签：`git tag`
- 创建标签时添加详细说明：`git tag -a <tagname> -m '<info>'`
- 创建标签时添加详细说明：`git tag -a <tagname> <commit id> -m '<info>'`