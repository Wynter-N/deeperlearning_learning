# ubuntu初始化
VMWare虚拟机 2204 LTS
## 更换国内镜像源
### 备份
`sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak`
sudo为超级用户权限
## 更新软件包
`sudo apt upgrade -y //-y可以跳过询问阶段`
## 设置静态ip
有时候我们会发现，Ubuntu 的 IP 地址会改变，如果后续有 SSH、Samba 等使用需求，这时就需要配置静态 IP 以保证这些功能的正常使用。<br>
参考链接: <br>
https://blog.csdn.net/qq_42417071/article/details/136328625?csdn_share_tail=%7B%22type%22:%22blog%22,%22rType%22:%22article%22,%22rId%22:%22136328625%22,%22source%22:%22qq_42417071%22%7D <br>
reboot 命令重启

## 配置C/C++和Python开发环境
vscode & pycharm<br>
参考链接1：https://blog.csdn.net/fangshuo_light/article/details/123635576 <br>
          BV1Vz4y1w7gS <br>
参考链接2：BV17p4y1A7ny <br>
在看第一个链接的时候发现使用这两行代码可以实现把win的文件拖拽到vmware<br>
`sudo apt-get autoremove open-vm-tools`<br>
`sudo apt-get install open-vm-tools-desktop`<br>

在配置vscode的时候出现了<br>
[1] + Done"/usr/bin/gdb" --interpreter=mi --tty=${DbgTerm} 0<"/tmp/Microsoft-MIEngine-In-ol5l5h3o.ssx" 1>"/tmp/Microsoft-MIEngine-Out-qgnfzclq.0ae"<br>
的提示信息，根据https://github.com/Microsoft/vscode-cpptools/issues/2922#去修改了externalConsole之后还是存在 很奇怪 不过[]好像从0变成1了<br>

### .deb文件下载
1.使用cd命令进入文件所在目录<br>
2.sudo dpkg -i filename.deb<br>

## 安装anaconda
参考链接：<br>
https://blog.csdn.net/qq_46311811/article/details/123524762 <br>
creat了一个虚拟环境 envsPace<br>
要注意conda的版本不能太低，会不兼容，出现问题。<br>
下载地址：https://repo.anaconda.com/archive/ <br>

### 使用rpm命令时提示下载，下载时需要用到root权限，提示Authentication failure，刚安装完，没有设置root用户密码导致的。<br>
使用
`sudo passwd`<br>
输入并设置密码即可<br>

## 安装opencv C++&Python两个版本
1. Python参考链接：https://cn.linux-console.net/?p=30668
2. C++参考链接:https://blog.csdn.net/qq_40342400/article/details/135552011   https://blog.csdn.net/xhtchina/article/details/126422425
   在下载的时候提示
   E: Package 'python-dev' has no installation candidate
   E: Unable to locate package python-numpy
   E: Unable to locate package libjasper-dev
   E: Unable to locate package libdc1394-22-dev
   `sudo apt-get install python3-dev python3-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-dev`
   参考链接中的指令修正
