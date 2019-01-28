---
layout: post
---

根据印象更新一下ubuntu安装过程

### 分区

50G给/，512M给boot，3G给swap，剩下给/home

然后会报错说什么引导会被修改，再给256M给efi就行

### 配环境

1. 修改 `/etc/apt/sources.list` 为tuna镜像源

   ```bash
   # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
   # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
   # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
   # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
   # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
   
   # 预发布软件源，不建议启用
   # deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
   # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
   ```

2. 无线网络在Y7000P机子上会挂，应该是硬件问题，使用命令 `sudo modprobe -r ideapad_laptop` 即可启动

3. `sudo apt remove libreoffice* thunderbird* && sudo apt update && sudo apt upgrade && sudo apt autoremove`

4. 安装驱动：`sudo ubuntu-drivers autoinstall`

5. `sudo add-apt-repository ppa:nilarimogard/webupd8; sudo apt install prime-indicator` 图形界面切换N卡

6. `sudo apt install git htop zsh vim tmux cmake curl axel openssh-server texlive-full gummi proxychains python-pip python3-pip libopencv-dev libboost-dev gnome-tweak-tool openvpn openssl mpv wine64 xclip enca apache2 php7.2 unrar ruby gnome-shell-extensions dos2unix xserver-xorg-input-synaptics libinput-tools xdotool icdiff g++-5 gcc-5 openjdk-11-jdk net-tools libglew-dev libcanberra-gtk-module libcanberra-gtk3-module tlp freeglut3 freeglut3-dev pandoc ttf-mscorefonts-installer binwalk; sudo gem install fusuma` 并安装oh-my-zsh 和.tmux

   ```bash
   # 如果是第一次
   sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
   cd
   git clone https://github.com/gpakosz/.tmux.git
   ln -s -f .tmux/.tmux.conf
   cp .tmux/.tmux.conf.local .
   # 如果装过了
   chsh -s /usr/bin/zsh
   ```

7. 安装 chrome、typora、sublime、teamviewer、wps-office、sogoupinyin、vmware

8. 修改 `~/.pip/pip.conf` 然后 `sudo pip3 install pip torch torchvision opencv-python tensorflow-gpu jupyter matplotlib ipython shadowsocks --upgrade `

9. 同时安装macbuntu

   ```bash
   sudo add-apt-repository ppa:noobslab/macbuntu
   sudo apt-get update
   sudo apt-get install macbuntu-os-icons-v1804 macbuntu-os-ithemes-v1804
   ```

10. 下载cuda9.0，选ubuntu16.04或者17.04版本的并安装，g++需要降级到g++-5之后再安装。下载5个run文件挨个执行。

   ```bash
   sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 10
   sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-5 10
   ```

11. 下载cudnn7.1.4匹配cuda9.0版本

   ```bash
   sudo cp include/cudnn.h /usr/local/cuda/include/
   sudo cp lib64/libcudnn* /usr/local/cuda/lib64/
   ```

12. 安装之后在 `~/.zshrc` 中添加

   ```bash
   export PATH=$PATH:/usr/local/cuda-9.0/bin
   export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-9.0/lib64
   ```

13. `sudo vim /usr/local/lib/python3.6/dist-packages/shadowsocks/crypto/openssl.py` 改52和111行改成 `libcrypto.EVP_CIPHER_CTX_reset` 不然ss起不起来

14. 开启apache2：

   ```bash
   cd /etc/apache2
   
   # first change document root
   vim apache2.conf
   # change line 170
   vim sites-available/000-default.conf
   # change line 12
   vim sites-available/default-ssl.conf
   # change line 5
   
   # then change php file upload conf
   cd /etc/php/7.2/apache2/
   vim php.ini
   # change line 383, 393, 404, 672, 825, 853
   ```

15. 禁止内核更新（防止双显示屏出bug），版本号要改为当前最新的内核版本

   ```bash
   sudo apt-mark hold linux-headers-4.15.0-43 
   sudo apt-mark hold linux-headers-4.15.0-43-generic 
   sudo apt-mark hold linux-image-4.15.0-43-generic 
   sudo apt-mark hold linux-modules-4.15.0-43-generic 
   sudo apt-mark hold linux-modules-extra-4.15.0-43-generic 
   ```


### 效果图

![](/images/htop.png)

