## 为什么磁盘IO延迟很高？



~~~shell
df # 发现要等好久才有输出

top # 查看发现iowait比较高，可以看看占用比较高的进程

ps aux # 看看进程

iostat -dx 1 # 查看到IO使用率很高，接近饱和了，

pidstat -d 1 # 查看到占用IO高的进程

strace -p 12280 -f # 跟踪进程甚至多线程和多进程可以跟踪是否有什么大量写操作，查看对应的文件

## 源码修改


~~~



