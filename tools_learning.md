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
