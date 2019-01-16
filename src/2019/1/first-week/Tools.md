# 记录chrome 和其他工具的使用和技巧

## chrome

- 恢复界面链接：`chrome://flags/#top-chrome-md` 在chrome的地址栏中输入回车


## git

回退到上一个提交:

`$ git reset --hard HEAD^`

回退到任意一个提交:

`$ git reset --hard commitID`

此时如果还保留着命令行, 且能找到log中已经消失的`commitID`, 则可以再次回滚到最新的.如果 关闭了, 且找不到 `commitId`, 则可以用:reflog 找到所有记录.

`$ git reflog`

### 遇到一个git本地回退和后远端仓库的问题

> 使用`git reset --hard commit ID` 后, 工作区的内容回退到以前的代码，但远程库里面没改变, 此时如果`git push`的话 会报错, 因为本地的比远程的旧, 根据提示需要先 `git pull`回来, 此时陷入的死循环.

  示例


假设一开始你的本地和远程都是：

a -> b -> c

你想把HEAD回退到b，那么在本地就变成了：

a -> b

这个时候，如果没有远程库，你就接着怎么操作都行，比如：

a -> b -> d

但是在有远程库的情况下，你push会失败，因为远程库是 a->b->c，你的是 a->b->d

两种方案：

1. push的时候用`--force`，强制把远程库变成a -> b -> d，大部分公司严禁这么干，会被别人揍一顿

2. 做一个反向操作，把自己本地变成a -> b -> c -> d，注意b和d文件快照内容一莫一样，但是commit id肯定不同，再push上去远程也会变成 a -> b -> c -> d

简单地说就是你无法容易地抹去远程库的提交信息，所以本地提交怎么都行，push前想好了

第二种方案 可以用: `git revert -n commit ID` 实现以退为进.
git revert 不同于 git reset  它不会擦除"回退"之后的 commit_id ,而是正常的当做一次"commit"，产生一次新的操作记录，所以可以push，不会让你再pull

