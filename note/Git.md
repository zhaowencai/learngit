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

8. 删除也是更改，可以git rm file然后git commit，或者git restore file从版本库恢复

9. 添加远程库 **git remote add origin git@github.com:zhaowencai/learngit.git**，把本地库的所有内容推送到远程库上：**git push -u origin master**

10. 要克隆一个仓库，首先必须知道仓库的地址，然后使用**git clone**命令克隆

11. 创建并切换到新的dev分支，可以使用**git switch -c dev**，直接切换到已有的master分支，可以使用：**git switch master**
    
12. Git鼓励大量使用分支：
- 查看分支：**git branch**
- 创建分支：**git branch <name>**
- 切换分支：**git checkout <name>**或者**git switch <name>**
- 创建+切换分支：**git checkout -b <name>**或者**git switch -c <name>**
- 合并某分支到当前分支：**git merge <name>**
- 删除分支：**git branch -d <name>**

13. 如果要丢弃一个没有被合并过的分支，可以通过**git branch -D <name>**强行删除

14. 多人协作：
- 查看远程库信息，使用git remote -v
- 从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交
- 在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致
- 建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name
- 从远程抓取分支，使用git pull，如果有冲突，要先处理冲突

15. 标签管理：
- 命令**git tag <tagname>**用于新建一个标签，默认为HEAD，也可以指定一个commit id；
- 命令**git -a <tagname> -m "blablabla..."**可以指定标签信息；
- 命令**git tag**可以查看所有标签。
- 命令**git push origin <tagname>**可以推送一个本地标签；
- 命令**git push origin --tags**可以推送全部未推送过的本地标签；
- 命令**git tag -d <tagname>**可以删除一个本地标签；
- 命令**git push origin :refs/tags/<tagname>**可以删除一个远程标签。