# CLI(命令行用户界面）
参考链接 <https://ss64.com/bash/>
1. `ls` 列举当前所在目录文件 `ls -a` 所有文件 包括隐藏文件 `ls /` 不再以当前目录为根目录 `ls -l`detailed
2. `pwd` 查询当前所在目录
3. `cd` 进入其他目录 `cd /build`
4. `echo " "` 输出" "中的字符
5. `cat fileNAme.txt` 输出.txt文件中的内容
6. `mv file1 file2` 移动文件.绝大多数命令可以通过加上一个`-v`来要求系统给出执行命令的反馈
7. `touch filename.txt` 新建空的文本文件
8. `mkdir file` 新建文件夹
9. `rm -i tempfile.txt` 删除 -i是让系统在执行删除操作时增加一行确认信息；也可以使用`alias rm='rm -i'`让-i成为默认参数
10. `ps`查询当前进程

# tmux工具使用
参考链接：<https://www.cnblogs.com/zhiminyu/p/17457933.html> 
#### to name but a few
 ![image](https://github.com/user-attachments/assets/e8e445a3-247f-4fdc-adb2-e45d276acfcb)
 1. 安装 `sudo apt-get install tmux`
 2. 启动与退出 `tmux`   `exit`或按下Ctrl+d
 3. 新建会话并命名 `tmux new -s <session-name> `
 4. 分离会话 `tmux detach` 或按下 Ctrl+b d  本条命令执行后，会退出当前窗口，但是会话仍在运行
 5. 查看当前所有tmux会话 `tmux ls` or `tmux list-session`
 6. 重新接入某个已存在的会话 <br>
     使用会话编号 `tmux attach -t 0` <br>
     使用会话名称 `tmux attach -t <session-name>` <br>
 7. 杀死会话 <br>
     使用会话编号 `tmux kill-session -t 0` <br>
     使用会话名称 `tmux kill-session -t <session-name>` <br>
 8. 切换会话 <br>
     使用会话编号 `tmux switch -t 0` <br>
     使用会话名称 `tmux switch -t <session-name>` <br>
 9. 划分窗格 <br>
     上下： `tmux split-window` <br>
     左右： `tmux split-window -h` <br>
 10. 切换光标 <br> 
`光标切换到上方窗格 tmux select-pane -U 光标切换到下方窗格 tmux select-pane -D `<br>
`光标切换到左边窗格 tmux select-pane -L 光标切换到右边窗格 tmux select-pane -R `<br>
 11. 列出所有快捷键 `tmux list-keys`

# SSH参考链接
<https://blog.csdn.net/jks212454/article/details/>
# gcc/g++ CMake/Make
1. 预处理，生成预编译文件（.i文件）：gcc –E main.c –o main.i
2. 编译，生成汇编代码（.s文件）：gcc –S main.i –o main.s
3. 汇编，生成目标文件（.o文件）：gcc –c main.s –o main.o
4. 链接，生成可执行文件（executable文件）：gcc main.o –o main
5. 参考链接 <https://blog.csdn.net/hjxu2016/article/details/83012946>
6. <https://blog.csdn.net/hjxu2016/article/details/101699484>
7. <https://blog.csdn.net/hjxu2016/article/details/102523522>

# 静态库和动态库
静态库将库代码静态地编译到可执行文件中，因此可执行文件的大小会增大；而动态库则是在运行时从共享库中加载所需的代码，因此可执行文件的大小较小。
静态库一旦被链接，其中所有的代码都不再发生更改；而动态库可以在程序运行时被升级或替换。
多个可执行文件可以使用同一个动态库，以减少内存占用和磁盘空间的使用。但每个可执行文件都需要包含其自己的静态库副本，因此可能会浪费大量的磁盘空间     
原文链接：<https://blog.csdn.net/qq_41979948/article/details/129693847>


   

