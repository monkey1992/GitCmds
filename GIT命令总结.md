# GIT命令

1.查看远程分支：

```
git branch -a
```

2.查看本地分支：

```git branch
git branch
```

3.本地创建分支：

```git branch <文件名>
git branch <branch name>
```

4.切换本地分支

```git checkout <branch name>
git checkout <branch name>
```

5.本地创建并关联远程对应的分支

```
git checkout -b <local branch name> origin/<remote branch name>
```

6.回滚到历史版本

```
git revert <SHA1>
```

7.在B分支上合并A分支

```
git checkout B
git merge A
```

8.还原改动过但未commit的文件

```
git checkout -- <file name>
```

9.还原改动过但是已commit的文件

```
git reset HEAD -- <file name>
```

10.通过shell的rm指令删除文件。执行完之后需要add和commit

```
rm <file>
```

11.通过git rm删除文件。执行完之后不需要add，直接commit了

```
git rm <file>
```

12.在git服务器上建立好远程仓库之后，将本地仓库与远程仓库关联起来

```
cd <Local Project>
git init
git add <file>...
git commit -m "commit message"
git remote add origin <remote url>
git push -u origin master
```

13.查看远程分支

```
git remote
```

14.查看远程分支详细信息

```git remote -v
git remote -v
```

15.本地创建分支

```
git checkout -b <branch name>
```

16.推送本地分支至服务器

```
git push origin <branch name>
```

17.删除本地分支

```git branch -d <branch name>
git branch -d <branch name>
```

18.强制删除本地分支

```
git branch -D <branch name>
```

19.本地创建tag

```git
git tag <tag name>
```

20.本地通过commit id指定位置创建tag

```git
git tag <tag name> <commit id>
```

21.创建带注释的tag

```
git tag -a <tag name> -m "message..." <commit id>
```

22.本地查看tag

```
git tag
```

23.推送某个tag到远程仓库

```
git push origin <tag name>
```

24.推送所有tag到远程仓库

```
git push origin --tags
```

25.删除本地tag

```
git tag -d <tag name>
```

26.删除远程仓库的tag，先删除本地tag，再推送到远程仓库

```
git tag -d <tag name>
git push origin :refs/tags/<tag name>
```

27.删除远程分支

```
git push origin --delete <branch name>
```

28.撤销已push的代码

```shell
git reset --soft <commitId> 
//--soft回会退到之前的版本，但是保留当前工作区的修改
或者
git reset --hard <commitId>
//--hard会抛弃当前工作区的修改

git push origin <branch name> --force // 不安全，会强制覆盖远端其他人的提交
git push origin <branch name> --force-with-lease // 安全，会强制覆盖远端其他人的提交
// 使用 git push --force-with-lease 命令被拒绝时，你需要 fetch 仓库，然后确认其他人是否对此分支有新的修改，如果没有，你才可以继续强制推送。
```
29.查看Git版本

~~~shell
git --version
~~~

30.查看当前一个项目的Git配置信息

~~~Shell
git config --list
~~~

31.查看所有Git项目的通用配置信息

~~~shell
git config --list --global
~~~

32.查看指定配置名的配置信息

~~~shell
git config <配置Key>
~~~

例如：

~~~shell
git config user.name
~~~

33.配置单个参数

~~~Shell
git config --global <配置key> <配置value>
~~~

例如:

~~~shell
git config --global user.name xxx
~~~

34.同时配置多个参数

~~~
git config --global --add <配置key1> <配置value1> <配置key2> <配置value2>
~~~

例如：

~~~
git config -- global --add user.name xxx user.email xxx@xxx.com
~~~

35.删除一个配置

~~~Shell
git config --global --unset <配置key> <配置value>
~~~

例如：

~~~Shell
git config --globale --unset user.name xxx
~~~

36.获取指定tag版本的代码

~~~Shell
git checkout <tag_name>
~~~

37.从指定tag版本的代码中恢复

~~~shell
git checkout master
~~~

38.使用了开源社区的代码，希望同步开源社区最新的代码

~~~Shell
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
39.添加新的remote

```shell
// 添加
git remote add <remote_name> <remote_url>
// 更新
git pull <remote_name> <remote_branch_name>
```

40.重命名本地分支

```shell
git branch -m <old_local_branch_name> <new_local_branch_name>
```

41.重命名远程分支

```shell
// 重命名远程分支对应的本地分支
git branch -m <old_local_branch_name> <new_local_branch_name>

// 删除远程分支
git push origin:<old_local_branch_name>

// 重新推送新命名的本地分支
git push origin <new_local_branch_name>
```

