# 第一次使用git命令提交代码
*  在新文件夹中使用 git init 命令

```sh
$ sudo git init
```
*  创建 README.md 文件

```sh
$ sudo touch README.md
```
*  使用 git commit 命令

```sh
$ sudo git commit -m "提交描述"
```
*  使用 git remote 增加一个新的远程仓库，并命名

```sh
$ sudo git remote add [仓库名称] [仓库地址]
```
*  取回远程仓库的变化，并与本地分支合并

```sh
$ sudo git pull [仓库名称] [分支名称]
```
* 上传本地指定分支到远程仓库

```sh
$ sudo git push [仓库名称] [分支名称]
```


[其他有用的命令](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
