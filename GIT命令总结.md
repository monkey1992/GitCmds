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

```
git reset --soft <commitId> 
//--soft回会退到之前的版本，但是保留当前工作区的修改
或者
git reset --hard <commitId>
//--hard会抛弃当前工作区的修改

git push origin <branch name> --force
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

