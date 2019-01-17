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


## sublime text3

### 打开 `Package Control` 的安装界面报错 : there are no package available for installation?

[参考自](https://www.cnblogs.com/jellify/p/9522477.html)
分析原因发现，在利用sublime进行插件下载时，sublime会调用channel_v3.json文件，点击Preferences->Package Setting->Package Control ->Setting Default，可以看到该文件是放置在网络中进行读取的，而由于GFW的原因，导致无法读取该文件（但是竟然可以直接访问？？），这也就是导致插件无法下载的原因
```json
默认的是这样的
	{    
	    "channels": [
	        "https://packagecontrol.io/channel_v3.json"
	    ]
	}

改为 本地的 json文件路径
	{    
	    "channels": [
	        "F:/subl/channel_v3.json"
	    ]
	}
```


我们在Preferences->Package Setting->Package Control ->Setting User 中，可以进行用户设置，我们可以将文件下载后，进行本地访问。首先访问https://packagecontrol.io/channel_v3.json ，将源代码复制后，新建文件为channel_v3.json（也可以从github中获取源文件），然后在Setting User设置中，添加代码，至此，就可以正常使用install package下载插件。
