<<Linux 鸟哥的私房菜>>  心得 ： 实践与观察才是王道
第0章 ： 计算机概论
 计算机 ： 接受用户输入的指令与数据，经过中央处理器的数据与逻辑单元运算处理后，以产生或存储成有用的信息。
 0.1.1 计算机硬件的五大单元 『 输入单元(鼠标，键盘等)， CPU(算术逻辑，控制，记忆)， 输出单元(屏幕，打印机等) 』
       CPU 为一个具有特定功能的芯片，里头含有微指令集。
       CPU 读取的数据都是从内存中读取来的，内存的数据是由输入单元传输进来的。CPU处理完毕的数据要写入内存，内存再到输出单元。
 0.1.3 接口设备 (只有cpu也无法运作计算机)
         主板(设备连接一起，让其协调，通信) - 
         存储设备(硬盘，软盘，光盘，磁带) - 硬盘最小物理量512bytes,最小的组成单位为扇区sector 
         显示设备 
         网络设备
 0.2 个人计算机的架构与设计
  x86开发商 (intel,AMD) 的cpu架构并不兼容，主板芯片组设计不相同。
   主板上最重要的就是芯片组，芯片组通常又分为两个桥接器来控制各组件的通信。
    北桥 : 负责连接较快的cpu,内存和显卡 等组件。 (AMD : 内存直接与cpu通信，不经过北桥)
    南桥 : 负责连接硬盘，USB，网卡等。
   北桥的总线称为系统总线，是内存传输的主要信道。
   与总线宽度类似，cpu每次能够处理的数据量称为字组大小(word size),字组大小依据cpu的设计而有32位与64位。
   0.2.3 显卡厂商直接在显卡上面嵌入一个3D加速的芯片，这就是GPU称谓的由来。
   0.2.6 CMOS是电脑主板上的一块可读写的RAM芯片。因为可读写的特性，
          所以在电脑主板上用来保存BIOS设置完电脑硬件参数后的数据，这个芯片仅仅是用来存放数据的。
           BIOS为写入到主板上某一块闪存或EEPROM的程序，在开机的时候运行，以加载CMOS当中的参数。
 0.3 软件是计算机的灵魂。
      机器程序与编译程序。 C/C++ ----编译器-----> 机器码
 0.4 操作系统 OS
      那如果我们能够将所有的硬件都驱动，并且提供一个开发软件的参考接口来给工程师开发软件的话，那就是OS。
     * OS 内核 『
        OS其实是一组程序，这组程序的重点在于管理计算机的所有活动以及驱动系统中的所有硬件。
        OS内核 -- 开机后常驻内存。
      』
    * 系统调用 System Call -- 开发软件，参考内核的相关功能。
     应用程序 -- 系统调用 -- OS内核 -- 硬件
   ** 内核功能 『
     1，系统调用接口
     2，程序管理
     3，内存管理
     4，文件系统管理
     5，设备驱动
    』
第 1 章 ： Linux是什么
 GNU (Richard Mathew Stallman - 史托曼) 伟大的人物。
 GNU 通用公共许可证 GPL - General Public License
   * Emacs
   * GCC (GNU C Compiler )
   * GLIBC (GNU C Library)
   * Bash shell
  Linus Torvalds - Linux 参考 Minix(from 谭宁邦教授) 
  Linux 参考了POSIX规范(可携式操作系统接口)，重点在于规范内核与应用程序之间的接口。
第 2 章 ： Linux如何学习
 从头学习 Linux 基础
  1，计算机概论与硬件相关知识
  2，先从Linux的安装与命令学起
  3，Linux操作系统的基础技能
  4，务必学会vi文本编辑器
  5，Shell与Shell脚本的学习
  6，一定要会软件管理员
  7, 网络基础的建立
  8, 这样网站的架设对你来说太简单了。
  实践再实践 -- 要增加自己的体力，就只有运动；要增加自己的知识，就只有读书。
  http://linux.vbird.org/
   Netman兄弟的建议 『
     (1) 有系统的设计文件目录
     (2) 养成一个做记录的习惯
   』  后研 - Linux 文件计划的网站是 http://tldp.org/
   鸟哥的建议 『 （1）建议兴趣 （2）成就感 (被认可，被认同) 』
第 3 章 ： Linux主机规划与磁盘分区
第 4 章 ： 安装 CentOS 5.x 多重引导小技巧
第 5 章 ： 首次登录与在线求助 man page
第 6 章 ： Linux的文件权限与目录配置
 Linux : 多用户，多任务环境。
  owner, group, others 且 各有 read, write, execute 等权限。
  /etc/passwd   /etc/shadow   /etc/group
 6.2.1 文件属性
 *1 文件处理命令  [ ls, cp, mv, rm, cat, ln, file]  文件内容查阅  [ cat, more, less, head, tail]
 *2 权限管理命令  [ chmod  u+r g-w o=x 777,  chown [-R] robby filename, chgrp 组名 filename, umask -S]
 *3 文件搜索命令  [ which, find, locate, updatedb, grep ]which -a命令在哪里,whereis -b（数据库）locate 显示所有
 *5 压缩解压命令  [ gzip, gunzip, tar, zip, bzip2]
 *6 网络通信命令  [ write, wall, ping, ifconfig] 
 *4 帮助命令     [ man, info, whatis  apropos, help]
 *7 系统关机命令  
 *8 Shell应用技巧
  whereis 与 which [不同是可以看到命令所在帮助文档位置]
  修改文件时间或创建新文件命令 ： touch
  drwxr-xr-x      2       hp      hp     4096    2012-12-25 16:18  dlinux
[文件类型与权限] [硬链接数] [所有者] [所属组] [文件容量]    [修改日期]      [文件名]

文件类型 d 目录directory  - 二进制文件  l 软链接文件link
    rwx         r-x        r-x  
   所有者u      所属组g     其他人o
   user        group      others
   (所有者可以转让)
第五部分 {
   4096 - 文件大小 [不是很准确，标记目录本身的大小，不是目录总大小] 数据块(512字节1单位)
   组织管理数据的方式，每种OS都有自己的，比如 NTFS, ext3 ...
   存储数据的最小单位就叫做数据块，这一这样理解！！
   文件向。。。存储的时候，至少要占用一个数据块。  （你就 60斤，也得做一个椅子，200斤做一个，600斤可能做两个！）
   分你做什么，数据块越小存取速度越小，数据块越大存取的时候浪费空间越大。
   分你做什么，调数据块多大合适。。。有个别时候！！
  }
文件搜索命令 详解 『
 *2 find
 (1) 命令所在路径 : /usr/bin/find  语法:find [搜索路径] [搜寻关键字]
   范例:
   $ find /etc -name init*  在目录/etc中查找init开头的文件
   $ find / -size +204800  在根目录下查找大于100MB的文件 block=512B
                  大于 ： +， 小于 ： - ， 等于 ： 不写 +, -；
   $ find / -user sam      在根目录下查找所有者为sam的文件
   find 原则 - 尽量节省系统资源
 (2) *1*   天     ctime, atime, mtime
     *2*   分钟   cmin , amin,  mmin
   c-change 改变， 表示文件属性被修改过，所有者，所属组，权限
   a-access 访问
   m-modify 修改， 表示文件内容被修改过
   -之内， +超过
   find /etc -mmin -120   我们刚讲了 4 个find的选项，其实不下 40 个！要学会看文档！
 (3) 连接符  -a and 逻辑与 -o or 逻辑或
   $ find /etc -ctime -1   在/etc下查找24小时内被修改过属性的文件和目录
   $ find /etc -size +163840 -a -size -204800    在/etc下查找大于80MB小于100MB的文件
   $ find /etc -name init* -a -type f [ 二进制文件 ]
   $ find /etc -name init* -a -type l [ 软链接文件 ]
    -type 文件类型  f 二进制文件  l 软链接文件  d 目录
    连接符 find ..... -exec 命令 {} \;
                           {} find 查询的结果  \ 转义符 【ls \ls】
  $ find /etc -name inittab -exec ls -l {} \; 解释 ： 在/etc下查找inittab文件并显示其详细信息
  $ find /test -name testfile3 -exec rm {} \;
  $ find /etc -name inittab -ok ls -l {} \;  能询问一下 -ok
  $ find /etc -name inittab -a -type f -exec ls -l {} \;
  $ find . -inum 16 -exec rm {} \;
 ------------------------------------------------------------------------------------------
 *3 locate [linux特有的 在文件数据库中查找 很快]
      语法:locate [搜索关键字]  功能描述:寻找文件或目录  范例: $ locate file  ** 列出所有跟file相关的文件
 *4 updatedb  执行权限:root  语法:updatedb  功能描述:建立整个系统目录文件的数据库  范例:# updatedb
 *5 grep  功能描述:在文件中搜寻字串匹配的行并输出  范例:# grep ftp /etc/services
』
帮助命令 {
 #1 man   man [会调用more] 
  范例: $ man ls  查看ls命令的帮助信息
  帮助分多种 ：第一种是命令，第五种是配置文件
  man 5 passwd  man passwd  man 1 passwd
 #2 info [linux特有的，和 man 只是呈现形式略有差别]
  语法:info [任何关键字]   范例: $ info ls  查看ls指令的帮助信息
 #3 whatis  apropos
  指令所在路径:/usr/bin/whatis apropos   /usr/sbin/makewhatis
  执行权限: All User,   All User,   root
  语法: whatis apropos [任何关键字]
  功能描述: 获得索引的简短说明信息
  范例: $ whatis ls
       $ apropos fstab  相当于man -k
  帮助指令:whatis
  范例: #make whatis
  建立whatis和apropos搜索使用的数据库,当使用这两个命令发生错误时,就是whatis database没有建立
 #4 help [查看shell内置命令的帮助]
     硬件 - 内核 - shell
     man bash[一个内置命令就行] 告诉你当前 shell 有哪些内置命令
}
6.2.4 Linux 文件种类与扩展名
  1, (普通文件，纯文本文件(ASCII)，二进制文件，数据格式文件)
  2, 目录
  3, 连接文件
  4, 设备与设备文件(b,c)   5, 套接字   6, 管道。
6.3 文件系统目录结构简介
/bin  : 基础系统所需要的最基础的命令就是放在这里。比如 ls、cp、mkdir等命令；
         功能和/usr/bin类似，这个目录中的文件都是可执行的，普通用户都可以使用的命令。
/boot : Linux的内核及引导系统程序所需要的文件。
         启动装载文件存放位置，如kernels,initrd,grub。一般是一个独立的分区。
/dev  :  一些必要的设备,声卡、磁盘等。还有如 /dev/null. /dev/console /dev/zero /dev/full 等。
/etc  :  系统的配置文件存放地. 
/home :  用户工作目录，和个人配置文件，如个人环境变量等.
/lib  :  库文件存放地。bin和sbin需要的库文件。类似windows的DLL。
/media : 可拆卸的媒介挂载点，如CD-ROMs、移动硬盘、U盘，系统默认会挂载到这里来。
/mnt  : 临时挂载文件系统。比如有cdrom 等目录。
/opt  : 可选的应用程序包。 第三方软件
/proc : 操作系统运行时，进程（正在运行中的程序）信息及内核信息（比如cpu、硬盘分区、内存信息等）存放在这里。
/root : Root用户的工作目录
/sbin : 和bin类似，是一些可执行文件，不过不是所有用户都需要的，一般是系统管理所需要使用得到的。
/tmp  : 系统的临时文件，一般系统重启不会被保存。
/usr  : 包含了系统用户工具和程序。
  /usr/bin ： 非必须的普通用户可执行命令
  /usr/include ： 标准头文件
  /usr/lib  : /usr/bin/ 和 /usr/sbin/的库文件
  /usr/sbin : 非必须的可执行文件
  /usr/src  : 内核源码
/srv : 该目录存放一些服务启动之后需要提取的数据
第 7 章 Linux 文件与目录管理
 处理目录命令 ： cd, pwd, mkdir, rmdir(删除空目录). bash shell(具有文件补齐tab)
 关于执行文件路径的变量 ： $PATH
  hp@ubuntu:~$ echo $PATH  /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games
 7.4.3 文件特殊权限 ： SUID， SGID， SBIT
   hp@ubuntu:~/2014$ ls -ld /tmp
   drwxrwxrwt 12 root root 4096  9月 30 21:39 /tmp
   hp@ubuntu:~/2014$ ls -ld /usr/bin/passwd
   -rwsr-xr-x 1 root root 42824  2月 11  2012 /usr/bin/passwd
   s 与 t 这两个权限与系统的帐号以及系统的进程较为相关。以后再研究。
第 8 章 Linux 磁盘与文件系统管理
第 9 章 文件与文件系统的压缩与打包
第 10 章 vim 程序编辑器
第 11 章 认识与学习bash
 Linux bash东西非常多，包括变量的设置与使用，bash操作环境的搭建，数据流重定向功能，还有那好用的管道命令。
 11.1.1 硬件, 内核 与 shell
   1, 硬件   2，内核程序   3，应用程序
   man, chmod, chown, vi, fdisk, mkfs等命令，这些命令都是独立的应用程序。
 11.1.2 shell 
        /etc/shells    /etc/paswd
 11.1.4 bash shell 的功能
  bash的主要优点 : 『
   (1) 命令记忆功能 (history)  .bash_history (注销系统后，命令记忆会记录到.bash_history)
   (2) 命令与文件补全功能 (tab)
   (3) 命令别名设置功能 (alias) alias lm='ls -al'
   (4) 作业控制，前台，后台控制 (job control, foreground, background)
   (5) 程序脚本 (shell script)
   (6) 通配符 (Wildcard)
  』
 11.1.5 bash shell的内置命令 ： type
  # type [-tpa] name
 11.1.6 命令的执行  "/Enter" 转义
 11.2 shell 变量 
      echo 变量显示  如 ： echo ${PATH}
      父子进程 export 设置成环境变量..
      unset 取消变量的设置值。 uname -r 显示内核版本
      "version=$(uname -r)" 来替代 "version=`uname -r`" 比较好。
 11.2.3 环境变量的功能
   env 与 export 查看环境变量
   HOME， SHELL， HISTSIZE， PATH， LANG(语系数据)， RANDOM(随机数发生器)
   export 自定义变量转成环境变量 export name
   子进程会定义父进程的环境变量，不会继承父进程的自定义变量
 11.2.5 变量的有效范围     基本上这样 『 环境变量=全局变量  自定义变量=局部变量』
 11.2.6 变量键盘读取，数组与声明： read, array, declare
    read -p "your name : " -t 30 named
    declare / typeset
    declare [-aixr] variable   数组，整数，环境变量，只读  declare +x sum(+可取消操作)
   hp@ubuntu:~/2014$ declare -i sum=1+3+5
   hp@ubuntu:~/2014$ echo $sum
hp@ubuntu:~/2014$ declare -ia var
hp@ubuntu:~/2014$ var[0]=3
hp@ubuntu:~/2014$ var[1]=4
hp@ubuntu:~/2014$ echo "${var[1]}, ${var[0]}"
4, 3
hp@ubuntu:~/2014$ var[2]=var[0]+var[1]
hp@ubuntu:~/2014$ echo "${var[1]}, ${var[2]}"
4, 7
 11.2.7 与文件系统及程序的限制关系 : ulimit
    bash 可以限制用户的某些系统资源，可打开的文件数量，可使用的CPU时间，可使用的内存总量等。
    ulimit -H -S -a -c -f -d -l -t -u -s 等。
 11.2.8 变量内容的删除，替代与替换
   #echo ${path/sbin/SBIN}
   ${变量#关键字}  ${变量##关键字}
   ${变量%关键字}  ${变量%%关键字}
   ${变量/旧字符串/新字符串}  ${变量//旧字符串/新字符串}  ...
 11.5 数据流重定向

--------
   
encoding cp936 -> utf-8

**example :**

```bash 
  iconv -f cp936 -t utf8 Contacts.txt -c > contacts—utf8.file
```
