克隆了某个项目之后，你也许想回顾下提交历史。 完成这个任务最简单而又有效的工具是 `git log` 命令。不传入任何参数的默认情况下，`git log` 会按时间先后顺序列出所有的提交，最近的更新排在最上面。 这个命令会列出每个提交的 SHA-1 校验和、作者的名字和电子邮件地址、提交时间以及提交说明。

若想查看某次提交中更详细的内容可以使用 `git show` 命令来进行查看。

## 任务

使用 <code exec="git log">git log</code> 命令查看我们克隆下来的项目的提交历史。

使用 <code exec="git show 'commit id'">git show 'commit id'</code> 命令来查看某次提交的具体修改内容(`' '`内的内容请根据实际情况进行修改)。