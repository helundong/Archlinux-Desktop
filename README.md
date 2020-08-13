# README

最近几年Linux软件质量越来越高，只要挑选合适的硬件，使用体验是非常不错的。

在这里记录一下日常使用经验，并备份部分dotfiles。

设备：联想小新pro13 2020 锐龙版 (4600u)

发行版：Archlinux

桌面环境：KDE

联想小新pro13 2020 锐龙版性能足够编程和日常使用，功耗低，轻度使用5小时以上，风扇噪音也小。内置的2k屏显示效果好，搭配27寸4k屏无不同dpi的困扰。

archlinux可定制化高，滚动更新，包管理器非常好用，软件最多。

KDE同样可定制化程度高。

##  0.系统安装

***略过***



##  1.软件安装

### 设置软件源

1. 使用国内镜像源代替国外源(增加下载速度)
2. 添加archlinuxcn源，其中有很多好用的软件

### 安装常用软件
1. 编程类：vmware idea openjdk vscode typora
2. 娱乐类：网易云音乐 vlc
3. 工具类 ：chrome 百度网盘 wechat v2rayA remmina mailspring latte-dock

## 2.字体配置

安装：pacman -S noto-fonts noto-fonts-cjk noto-fonts-extra ttf-liberation

配置~/.config/fontconfig/fonts.conf

kde设置字体为无衬线 

## 3.提高性能

1. 关闭默认的baloo：

   ​	使用balooctl disable禁止baloo，或者在设置->查找->文件搜索->启用文件搜索禁止baloo。baloo会定期索引，消耗资源，索引还占用空间，关键是中文不能分词，搜索不到文件，使用体验很差。关闭后使用dolphin搜索时重新搜索，速度会比较慢，但是可以分词，偶尔使用效果还是不错。另外可以使用Albert，中英文分词体验良好。

## 4.提升屏幕空间&效率

1. 使用latte-dock:

   安装: sudo pacman -S latte-dock

   latte-dock可以使用meta+num快速打开或者切换dock上的应用，短按meta打开启动器，长按meta显示应用对应的快捷键。

 2. 使用appmenu+title+button

    安装及使用方法可参考作者说明或[点击这里](https://impressionyang.gitee.io/2020/02/29/unity-style-applet/#applet-window-title)

    [applet-window-appmenu](https://github.com/psifidotos/applet-window-appmenu)

     [applet-window-title](https://github.com/psifidotos/applet-window-title)

    [applet-window-buttons](https://github.com/psifidotos/applet-window-buttons)

##  5.保存信息、密码

1. [Akonadi](https://wiki.archlinux.org/index.php/KDE#Akonadi) 

   kde相关程序保存信息 例如kmail，默认使用mysql保存，mysql版本不能太高

   

2. [KDE Wallet](https://wiki.archlinux.org/index.php/KDE_Wallet)

   部分程序使用kde的钱包程序保存密码，例如kde环境的wifi、idea中数据库连接
   可在钱包管理程序中设置密码为空可避免每次都需要输入密码
3. [Gnome-keyring](https://wiki.archlinux.org/index.php/GNOME/Keyring)
	部分gtk程序使用gnome-keyring保存密码 例如mailspring 可以使用[seahorse](https://wiki.archlinux.org/index.php/GNOME/Keyring#Manage_using_GUI) 通过GUI管理 例如设置密码为空可避免每次都需要输入密码

## 6.摸鱼

### VLC

播放windows共享内容：
   在dolphin 网络中添加网络地址
   安装kio相关依赖，不全可能导致某些文件打不开，[kio](https://wiki.archlinux.org/index.php/KDE#Samba/Windows_support)不如隔壁gnome家的[gvfs-smb](https://www.archlinux.org/packages/?name=gvfs-smb) 
   在vlc->设置->输入/编解码器->访问模块->SMB配置账号信息 域一般为WORKGROUP

## 7.其他

