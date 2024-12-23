# CLI(命令行用户界面）
参考链接 <https://ss64.com/bash/>
1. `ls` 列举当前所在目录文件 `ls -a` 所有文件 包括隐藏文件 `ls /` 不再以当前目录为根目录 `ls -l`detailed
2. `pwd` 查询当前所在目录
3. `cd` 进入其他目录 `cd /build`
4. `cd ..` 返回上一级目录
5. `echo " "` 输出" "中的字符
6. `cat fileNAme.txt` 输出.txt文件中的内容
7. `mv file1 file2` 移动文件.绝大多数命令可以通过加上一个`-v`来要求系统给出执行命令的反馈
8. `touch filename.txt` 新建空的文本文件
9. `mkdir file` 新建文件夹
10. `rm -i tempfile.txt` 删除 -i是让系统在执行删除操作时增加一行确认信息；也可以使用`alias rm='rm -i'`让-i成为默认参数
11. `ps`查询当前进程
12. <https://www.runoob.com/linux/linux-command-manual.html>
13. `find .` <https://www.runoob.com/linux/linux-comm-find.html> 查找文件 
14. `grep` <https://www.runoob.com/linux/linux-comm-grep.html> 查找内容包含指定的范本样式的文件
15. `xargs xc -l` <https://www.runoob.com/linux/linux-comm-xargs.html> 管道输出？
16. `sort` <https://www.runoob.com/linux/linux-comm-sort.html> 对文件进行排序
17. `uniq` <https://www.runoob.com/linux/linux-comm-uniq.html>  删除相同行

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
5. 使用gcc直接编译：gcc -c test.c //-> *.o   <br>
   gcc -o test.exe test.o
6. 参考链接 <https://blog.csdn.net/hjxu2016/article/details/83012946>
7. <https://blog.csdn.net/hjxu2016/article/details/101699484>
8. <https://blog.csdn.net/hjxu2016/article/details/102523522>
9. <https://developer.aliyun.com/article/1472509> ubuntu下使用makefile编译c语言程序工程
10. make all	编译所有目标
11. make -j	使用所有的核心编译目标
12. make -j8	使用8个核心编译目标
13. make install	安装已编译的程序
14. make uninstall	卸载已安装的程序
15. make clean	删除由make命令产生的文件，通常删除目标文件.o
16. make distclean	删除由./configure产生的文件
17. make check	测试刚编译的软件
18. make installcheck	检查安装的库和程序
19. make dist	重新打包成packname-version.tar.gz
20. 执行make命令时需要一个makefile文件，告诉make该如何编译和链接程序
21. makefile每条规则格式：<br>
`<target>: <prerequisites>`<br>
`[Tab]<commands>` <br>
 目标文件：依赖文件 <br>
     要执行的命令 <br>  告诉make文件的依赖是什么，要如何生成文件
23. 判断语句
    - else endif  条件判断
    - ifeq  值相等
    - ifneq
    - ifdef  值存在
    - ifndef
24. 提示：*** missing separator (did you mean TAB instead of 8 spaces?).  Stop  缩进用TAB键
25. makefile
    - 一般把编译和链接分开来写 .c-> .o -> 可执行文件
    - 对于更新时间晚于生成的文件的规则，不会重新编译
    - clean :用来清理编译过程中生成的过程文件或者可执行文件  若本地目录下有一个叫做clean的文件时clean命令会失效  -->
    - .PHONY:伪目标
    - all: make默认执行第一个规则，添加一个all
    - make filename:单独编译  make hello (e.g.)
    - 
   



# 静态库和动态库
静态库将库代码静态地编译到可执行文件中，因此可执行文件的大小会增大；而动态库则是在运行时从共享库中加载所需的代码，因此可执行文件的大小较小。
静态库一旦被链接，其中所有的代码都不再发生更改；而动态库可以在程序运行时被升级或替换。
多个可执行文件可以使用同一个动态库，以减少内存占用和磁盘空间的使用。但每个可执行文件都需要包含其自己的静态库副本，因此可能会浪费大量的磁盘空间   
原文链接：<https://blog.csdn.net/qq_41979948/article/details/129693847>


# git工具使用
1. 初始化仓库 git init
2. git add .  | git add . --all //提交文件/所有文件
3. git commit -m "文件描述信息"
4. git remote add origin +.git地址  链接远程仓库 创建主分支
5. git pull origin master //把本地仓库的变化连接到远程仓库的主分支
6. git push -u origin master //把本地仓库的文件推送到远程仓库
7. git remote remove origin  //取消链接
8. git remote -v //查看当前连接的远程仓库
9. git branch -m <name> //创建分支
10. 分支参考链接（在已经连接远程仓库的情况下）：<https://worktile.com/kb/ask/284935.html>







   

