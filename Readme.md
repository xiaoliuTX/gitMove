# gitMove

**git mv**

> Git has a rename command git mv, but that is just for convenience. The effect is indistinguishable from removing the file and adding another with different name and the same content.

`git mv`只是一个快捷用法，等同于git remvoe old & git add new。此方法移动文件提交后会导致之前的记录丢失

**git filter-branch**

[详细参考地址](https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E9%87%8D%E5%86%99%E5%8E%86%E5%8F%B2)

使用git filter-branch进行log重写的有个方便的脚本，见[链接](https://gist.github.com/emiller/6769886)

使用此方法重命名文件或移动文件时，有较严重的性能问题，重写操作非常耗时，对于中大型项目来讲无法忍受。

`官方推荐`git filter-branch 有很多陷阱，不再推荐使用它来重写历史。 请考虑使用 git-filter-repo，它是一个 Python 脚本，相比大多数使用 filter-branch 的应用来说，它做得要更好。

**git filter-repo** 

[项目主页](https://github.com/newren/git-filter-repo)

1.安装

```
pip3 install git-filter-repo
```

2.移动目录/重命名文件

```
git filter-repo --path --path-rename OLD_NAME:NEW_NAME
```

注意一定要在.git文件所在目录下执行此命令。

3.重新添加orgin并强推

```

```