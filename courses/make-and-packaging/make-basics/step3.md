下面我们将尝试使用刚刚编写好的 `Makefile` 来进行项目的编译

## 任务

删除上一步中产生的 `*.o` 文件：

<code exec="rm -f *.o">rm -f *.o</code>

执行 <code exec="make">make</code> 进行编译，此时 make 会读取 makefile 的内容，并根据内容直接编译相关的文件

执行 <code exec="./main">./main</code> 并与程序进行交互，查看程序执行结果。

## Tips

上面的执行，从命令行输出来看，获取你会觉得 shell script 也可以做到，的确是这样，但是 make 提供了增量编译的机制，不需要你自己去写那么复杂的流程判断了。好处如下：

简化编译时所需要下达的指令
若在编译完成之后，修改了某个源码文件，则 make 仅会针对被修改了的文件进行编译，其他的 object file 不会变动
最后可以依照相依性来更新（update）执行文件