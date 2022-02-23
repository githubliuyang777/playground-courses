上一节内容的最后我们了解到对于依赖复杂的项目来说，手动完成所有依赖的安装是非常困难的，如果能有工具帮助我们完成这样的工作就好了。

DNF(Dandified YUM)就是RPM软件包体系下的这样一款工具，DNF通过分析 RPM 的标头数据后，根据各软件的相关性制作出依赖时的解决方案，然后可以自动处理软件的依赖问题，以解决软件安装或移除或升级的问题。

操作系统发行版首先将软件打包成RPM软件包，然后将软件放置于YUM(DNF的上一代)服务器上，提供客户端的使用。因此我们想要使用DNF的功能时，必须要先找到适合的 yum server 才行，而每个 yum server 可能都会提供许多不同的软件功能，这就"软件库(Repo, Repository)"。


## 任务

1. 执行 <code exec="vim /etc/yum.repos.d/openEuler.repo">vim /etc/yum.repos.d/openEuler.repo</code>创建并编辑yum repo配置文件。

2. 按照下面的内容进行配置，该命令将会创建一条指向 `openEuler-21.09 Everything` 软件仓库的配置：

    ```
    [everything]
    name=everything
    baseurl=http://repo.openeuler.org/openEuler-21.09/everything/$basearch/
    enabled=1
    gpgcheck=1
    gpgkey=http://repo.openeuler.org/openEuler-21.09/everything/$basearch/RPM-GPG-KEY-openEuler

    ```

3. 执行 <code exec="dnf update">dnf update</code> 刷新目录

4. 执行 <code exec="dnf install -y bc">dnf install -y bc</code> ，可以看到 `bc` 和它所需要的依赖被一并安装了。