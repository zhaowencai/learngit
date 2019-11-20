## Git

1. Git是目前世界上最先进的分布式版本控制系统

2. 初始化一个Git仓库，使用**git init**命令。

3. 添加文件到Git仓库（或者提交修改到仓库），分两步：
- 使用命令**git add <file>**，注意，可反复多次使用，添加多个文件；
- 使用命令**git commit -m <message>**，完成。

4. 要随时掌握工作区的状态，使用**git status**命令。如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

5. **git log <--pretty=oneline>** 查看历史记录

6. 版本回退（切换） **git reset --hard commit_id**

7. 撤销更改：
- 场景一：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令**git checkout -- file**
- 场景二：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令**git reset HEAD <file>**，就回到了场景1，第二步按场景1操作