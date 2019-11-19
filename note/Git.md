## Git

1. Git是目前世界上最先进的分布式版本控制系统

2. 初始化一个Git仓库，使用**git init**命令。

3. 添加文件到Git仓库（或者提交修改到仓库），分两步：
- 使用命令**git add <file>**，注意，可反复多次使用，添加多个文件；
- 使用命令**git commit -m <message>**，完成。

4. 要随时掌握工作区的状态，使用**git status**命令。如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

5. **git log <--pretty=oneline>** 查看历史记录

6. 版本回退（切换） **git reset --hard commit_id**

7. 