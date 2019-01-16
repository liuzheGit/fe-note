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