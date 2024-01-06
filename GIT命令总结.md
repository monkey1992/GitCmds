# GIT命令

### 1.查看远程分支：

```bash
git branch -a
```

### 2.查看本地分支：

```bash
git branch
```

### 3.本地创建分支：

```bash
git branch <branch name>
```

### 4.切换本地分支

```bash
git checkout <branch name>
```

### 5.本地创建并关联远程对应的分支

```bash
git checkout -b <local branch name> origin/<remote branch name>
```

### 6.回滚到历史版本

```bash
git revert <SHA1>
```

### 7.在B分支上合并A分支

```bash
git checkout B
git merge A
```

### 8.还原改动过但未commit的文件

```bash
git checkout -- <file name>
```

### 9.还原改动过但是已commit的文件

```bash
git reset HEAD -- <file name>
```

### 10.通过shell的rm指令删除文件。执行完之后需要add和commit

```bash
rm <file>
```

### 11.通过git rm删除文件。执行完之后不需要add，直接commit了

```bash
git rm <file>
```

### 12.在git服务器上建立好远程仓库之后，将本地仓库与远程仓库关联起来

```bash
cd <Local Project>
git init
git add <file>...
git commit -m "commit message"
git remote add origin <remote url>
git push -u origin master
```

### 13.查看远程分支

```bash
git remote
```

### 14.查看远程分支详细信息

```bash
git remote -v
```

### 15.本地创建分支

```bash
git checkout -b <branch name>
```

### 16.推送本地分支至服务器

```bash
git push origin <branch name>
```

### 17.删除本地分支

```bash
git branch -d <branch name>
```

### 18.强制删除本地分支

```bash
git branch -D <branch name>
```

### 19.本地创建tag

```bash
git tag <tag name>
```

### 20.本地通过commit id指定位置创建tag

```bash
git tag <tag name> <commit id>
```

### 21.创建带注释的tag

```bash
git tag -a <tag name> -m "message..." <commit id>
```

### 22.本地查看tag

```bash
git tag
```

### 23.查看远程所有tag

```bash
git ls-remote --tags origin
```

### 24.拉取远程仓库的所有tag

```bash
git fetch --tags
```

### 25.推送某个tag到远程仓库

```bash
git push origin <tag name>
```

### 26.推送所有tag到远程仓库

```bash
git push origin --tags
```

### 27.删除本地tag

```bash
git tag -d <tag name>
```

### 28.删除远程仓库的tag，先删除本地tag，再推送到远程仓库

```bash
git tag -d <tag name>
git push origin :refs/tags/<tag name>
```

### 29.删除远程分支

```bash
git push origin --delete <branch name>
```

### 30.撤销已push的代码

```bash
git reset --soft <commitId> 
//--soft回会退到之前的版本，但是保留当前工作区的修改
或者
git reset --hard <commitId>
//--hard会抛弃当前工作区的修改

git push origin <branch name> --force // 不安全，会强制覆盖远端其他人的提交
git push origin <branch name> --force-with-lease // 安全，不会强制覆盖远端其他人的提交
// 使用 git push --force-with-lease 命令被拒绝时，你需要 fetch 仓库，然后确认其他人是否对此分支有新的修改，如果没有，你才可以继续强制推送。
```
### 31.查看Git版本

~~~bash
git --version
~~~

### 32.查看当前一个项目的Git配置信息

~~~bash
git config --list
~~~

### 33.查看所有Git项目的通用配置信息

~~~bash
git config --list --global
~~~

### 34.查看指定配置名的配置信息

~~~bash
git config <配置Key>
~~~

例如：

~~~bash
git config user.name
~~~

### 35.配置单个参数

~~~bash
git config --global <配置key> <配置value>
~~~

例如:

~~~bash
git config --global user.name xxx
~~~

### 36.同时配置多个参数

~~~bash
git config --global --add <配置key1> <配置value1> <配置key2> <配置value2>
~~~

例如：

~~~bash
git config -- global --add user.name xxx user.email xxx@xxx.com
~~~

### 37.删除一个配置

~~~bash
git config --global --unset <配置key> <配置value>
~~~

例如：

例如：

```bash
git config --globale --unset user.name xxx
```

### 38.获取指定tag版本的代码

~~~bash
git checkout <tag_name>
~~~

### 39.从指定tag版本的代码中恢复

~~~bash
git checkout master
~~~

### 40.使用了开源社区的代码，希望同步开源社区最新的代码

~~~bash
// 查看是否有upstream fetch 和 upstream push 两栏信息
git remote -v
// 如果没有，即没有原作者项目的url，需要自己添加
git remote add upstream <开源社区项目的URL>
// 获取从上游仓库（开源社区项目）的各分支
git fetch upstream
// 切换本地项目到主分支(master)
git checkout master
// 合并upstream/master远程分支到本地项目master分支
git merge upstream/master
~~~
### 41.添加新的remote

```bash
// 添加
git remote add <remote_name> <remote_url>
// 更新
git pull <remote_name> <remote_branch_name>

// 注：更新代码之前可以新增一个本地分支对应到新的remote，防止本地代码合并到新的remote的代码
```

### 42.重命名本地分支

```bash
git branch -m <old_local_branch_name> <new_local_branch_name>
```

### 43.重命名远程分支

```bash
// 重命名远程分支对应的本地分支
git branch -m <old_local_branch_name> <new_local_branch_name>

// 删除远程分支
git push origin:<old_local_branch_name>

// 重新推送新命名的本地分支
git push origin <new_local_branch_name>
```

### 44.备份当前的工作区的内容，从最近的一次提交中读取相关内容，让工作区保证和上次提交的内容一致。同时，将当前的工作区内容保存到Git栈中

~~~bash
git stash/git stash save "message..."
~~~

### 45.显示Git栈内的所有备份，可根据这个列表来决定从备份版本恢复

~~~bash
git stash list
~~~

### 46.恢复保存的工作进度，如果不使用任何参数，会恢复最新保存的工作进度，并将恢复的工作进度从存储的工作进度列表中清除;如果提供参数，则从该 `<stash>` 中恢复，恢复完毕也将从进度列表(栈)中移除 `<stash>`

~~~bash
git stash pop [--index][<stash>]
~~~

### 47.其作用和`git stash pop`类似，但不删除恢复的进度

~~~bash
git stash apply [--index][stash_id]
~~~

### 48.清空Git栈，即删除所有备份

~~~bash
git stash clear
~~~

### 49.将 B 分支重置为 A 分支

```bash
git checkout B
git reset --hard A
git push origin B --force
```

