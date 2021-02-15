2021年，ubuntu安装deepin-wine， 多数的教程都已经失效了，重新整理了一下

参考 https://gitee.com/wszqkzqk/deepin-wine-for-ubuntu


自己随便建立一个xxx.sh 复制下面的内容 给执行权限，运行就自动安装了，也可以直接下载我的install.sh给权限运行就可以了。

#!/bin/bash

mkdir ./deepintemp

cd ./deepintemp

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine/deepin-wine_2.18-22~rc0_all.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine/deepin-wine32_2.18-22~rc0_i386.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine/deepin-wine32-preloader_2.18-22~rc0_i386.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine-helper/deepin-wine-helper_1.2deepin8_i386.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine-plugin/deepin-wine-plugin_1.0deepin2_amd64.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine-plugin-virtual/deepin-wine-plugin-virtual_1.0deepin3_all.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine-uninstaller/deepin-wine-uninstaller_0.1deepin2_i386.deb

wget http://packages.deepin.com/deepin/pool/non-free/u/udis86/udis86_1.72-2_i386.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine/deepin-fonts-wine_2.18-22~rc0_all.deb

wget http://packages.deepin.com/deepin/pool/non-free/d/deepin-wine/deepin-libwine_2.18-22~rc0_i386.deb

wget https://packages.deepin.com/deepin/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_1.5.1-2_amd64.deb --no-check-certificate

wget https://packages.deepin.com/deepin/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_1.5.1-2_i386.deb --no-check-certificate

echo '准备添加32位支持'
sudo dpkg --add-architecture i386
echo '添加成功，准备刷新apt缓存信息...'
sudo apt update
echo '即将开始安装...'
sudo dpkg -i *.deb
echo '安装完成，正在自动安装依赖...'
sudo apt install -fy

rm -vfr ./deepintemp


以下不要复制

如果出现 wget 失败，可以运行直接克隆我的上面12个deb文件
git clonehttps://gitee.com/ch0769/deepin-wine.git
下面一行一行输入命令就可以了
echo '准备添加32位支持'
sudo dpkg --add-architecture i386
echo '添加成功，准备刷新apt缓存信息...'
sudo apt update
echo '即将开始安装...'
sudo dpkg -i *.deb
echo '安装完成，正在自动安装依赖...'
sudo apt install -fy





深度软件包下载地址 http://packages.deepin.com/deepin/pool/non-free/d/

我只用了几个
tim
deepin.com.qq.office_2.0.0deepin4_i386.deb
讯雷
deepin.com.thunderspeed_7.10.35.366deepin18_i386.deb
 微信
 deepin.com.wechat_2.6.8.65deepin0_i386.deb


下载好所需的deb软件终端打开软件的文件夹
输入sudo dpkg -i *.deb
自动安装依赖
sudo apt install -fy












