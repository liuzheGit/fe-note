## win10

1.创建新的虚拟桌面：Win + Ctrl + D

2.关闭当前虚拟桌面：Win + Ctrl + F4

3.切换虚拟桌面：Win + Ctrl +左/右

## chrome 

1. 打开最近关闭的标签`Ctrl + Shift + t`


## git

### 小总结
因为暂存区的从头顶，撤销修改分几种情况：
- 修改后， 文件没有放进暂存区，用`git checkout --文件名`撤销工作区的改动到上一次commit
- 修改过后， 文件放进暂存区(git add)， 且没有再次修改， 分两步：1.用`git reset <文件名>`撤销add操作
然后用`git checkout --文件名`撤销工作区
- 修过后， 文件放到暂存区，且又修改过了，

- 用 `git checkout -b newbranch`来创建并切换到新分支
### git删除本地和远程分支
本地：`git branch -d name`
远程： `git push origin --delete name`