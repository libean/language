## ubuntu安装后做得几件事情

    如仅仅个人使用，我不建议安装什么更新或者重要安全更新，除非有个人需要。觉得安装更新后，开机会变慢，我安的安全更新就这样。
   (如安装后有提示语言包不完整，则可按照提示安装好)

   1, 安装中文输入法 - http://blog.csdn.net/robby_chan下ubuntu/win文章(ibus-setup 可调热键)
   2, 安装 chrome 浏览器 (自带或者根据提示安装 flash) 
        (如使用Firefox 可以 sudo apt-get install flashplugin-installer 安装flash插件)
   3, 安装 gcc / g++。（gcc一般自带）[apt-get install g++]
   4, 安装 vim 继而配置 vim 配置文件 ～/.vimrc [apt-get install vim]
   5, 安装IDE geany (源文件最好存在本系统的目录上，最好不要存在win下的盘上)
   6, 对开机速度不满意者 --> 提高系统和开机速度。见本blog其他文章。
   7, 安装音乐播放器 sudo apt-get install audacious（类千千静听）插件会自动安装完成。用audacious听mp3非常棒。
   8，安装视频播放器 sudo apt-get install smplayer (推荐smplayer) (自带的不好)
   9，安装编辑器scribes  sudo apt-get install scribes
   10，如要卸载自带的音乐或视频播放器，可在软件中心卸载或者查看 More info 知道其包名，然后命令卸载
       如要使用自带的播放器，需要增加相应插件和解码器-自己研究吧。
   11, 安装飞信可在软件中心找 OpenFetion
   12, 软件中心 安装 Gnome Gmail / Gmail Notify
   13，ubuntu 用华为网卡建立Mobile Broadband  id : card mi : card 
   14, 安装Git 分布式版本控制工具。Github 是一个代码托管网站. sudo apt-get install git
       git clone https://github.com/robby0/Icpc.git icpc  远程clone

------------------------------------------------------------------------------------
## apt-get 详解
  
  卸载软件2：
    #apt-get remove packagename
  这会卸载相应的软件，同时也会卸载依赖的部分，没办法指定不卸载依赖的。但是 软件的配置文件还是会留在系统中。
  完全卸载软件包括删除配置：
    apt-get  --purge remove packagename
  这样配置文件也会被删除， purge 意思是 ： 清洗
    apt-get update
---------------------------------
## 快捷键
 1, 锁屏 ： Ctrl + Alt + l
 2, 显示隐藏的文件 ： Ctrl + h
 3, 不用右击鼠标就能显示文件属性 - 选中文件 -> Alt + Enter
