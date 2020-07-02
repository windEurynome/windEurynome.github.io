---
layout: post
title: "github的上传步骤"
data: 2020-07-02 17:53:40
categories: github
tags: github 上传
excerpt: github文件上传相关,作个记录，免得天天到处查找。原文链接：https://blog.csdn.net/littlely_ll/article/details/80054481
mathjax: true
---



**由于自己不经常上传github，上传的时候老是忘记命令或步骤，所以在这记录一下github上传步骤。**
```
	1:在github上新建一个仓库，创建时有一个https地址，记录此地址，后面用打开git bash，转到你所要上传的文件夹目录下，并输入git init将项目添加到仓库中去：git add .，如果添加某个文件，可以使用git add xxx
	2:将添加的文件提交到仓库：git commit -m "--注释--"
	3:将仓库关联到github：git remote add origin https://xxxx，https为刚才github上创建仓库的地址
	把文件推送到github仓库：git push -u origin master，下次推送时，可以把-u去掉
```

**如何在README.md里展示图片呢？**
```
	1:首先把图片提交到github，记录该图片所在的地址：https://xxx
	2:在README.md中添加图片：![](https://xxx)
```

**解决误上传问题**
```
	在修改一个文件(假设是readme.txt)后，把它添加到仓库(git add readme.txt)，并且提交到缓存区(git commit -m ‘’)，但是发现文件修改错了，想回到上一个没有被修改的版本，可以使用git checkout -- readme.txt撤回原来的修改。
```

**删除文件**
```
	git rm file #或删除文件夹 git rm -r filepath，删除本地文件或文件夹
	git commit -m 'delete'
	git push #删除远程仓库文件
```

**新建分支**
```
	1.新建分支	git branch tests
	2.切换分支	git checkout tests
```

  可以直接创建并切换到分支git checkout -b tests。切换分支后可以对分支的内容进行增加修改与提交。分支最初提交的时候可能会出现：
  ```
	fatal: The current branch tests has no upstream branch.
	To push the current branch and set the remote as upstream, use
    git push --set-upstream origin tests
  ```

这是没有将本地的分支与远程仓库的分支进行关联，所以要使用git push --set-upstream origin tests。

**分支合并**
```
	git checkout master
	git merge tests
```
  这样tests分支就合并到master上了。详细可参考Git 分支 - **分支的新建与合并。**

**删除分支**
  分支合并后，此分支可能不再需要了，则可以删除它。
```
	git branch -d tests
```
  !!使用上述命令需要先切换到别的分支去，否则会出现错误：
```
	error: Cannot delete branch 'tests' checked out at 'F:/xxx/xxx'。
```
  !!此时删除的是本地分支，要删除远程仓库分支则:
```
	git push origin :test或者
	git push origin --delete tests
```


