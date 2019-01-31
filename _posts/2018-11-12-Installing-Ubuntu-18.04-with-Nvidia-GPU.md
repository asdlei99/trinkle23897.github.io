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
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
   deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
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

15. 禁止内核更新（防止双显示屏出bug）

   ```bash
   sudo apt-mark hold linux-generic                        
   sudo apt-mark hold linux-headers-generic
   sudo apt-mark hold linux-image-generic  
   sudo apt-mark hold linux-signed-generic 
   ```


### 效果图

![](/images/htop.png)

### Bash Script

```bash
#!/bin/bash

echo "deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse" > /etc/apt/sources.list
apt remove -y libreoffice* thunderbird* && apt update && apt -y upgrade && apt -y autoremove
apt install -y htop
ubuntu-drivers autoinstall
apt install -y ruby python-pip python3-pip
gem install fusuma &
pip3 install pip torch torchvision opencv-python tensorflow-gpu jupyter matplotlib ipython shadowsocks mitmproxy bs4 gpustat scikit-image --upgrade &
cd /data/install
dpkg -i google-chrome-stable_71.0.3578.98-1_amd64.deb macbuntu-os-icons-v1804_3.3\~bionic\~NoobsLab.com_all.deb macbuntu-os-ithemes-v1804_3.3\~bionic\~NoobsLab.com_all.deb netease-cloud-music_1.1.0_amd64_ubuntu.deb sogoupinyin_2.2.0.0108_amd64.deb sublime-text_3176_amd64.deb typora_0.9.62-1_amd64.deb wps-office_10.1.0.6757_amd64.deb wps-office-fonts_1.0_all.deb
apt install -f -y
./VMware-Workstation-Full-14.1.1-7528167.x86_64.bundle &
# ZC5XK-A6E0M-080XQ-04ZZG-YF08D 
apt install -y git zsh vim tmux cmake curl axel openssh-server gummi proxychains libopencv-dev libboost-dev gnome-tweak-tool openvpn openssl mpv xclip enca apache2 php7.2 unrar gnome-shell-extensions dos2unix xserver-xorg-input-synaptics libinput-tools xdotool pandoc icdiff g++-5 gcc-5 openjdk-11-jdk net-tools libglew-dev libcanberra-gtk-module libcanberra-gtk3-module tlp freeglut3 freeglut3-dev pandoc ttf-mscorefonts-installer ansible binwalk
chsh trinkle -s /usr/bin/zsh
update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 10
update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-5 10
cd cuda9.0
./cuda_9.0.176_384.81_linux-run
./cuda_9.0.176.1_linux-run
./cuda_9.0.176.2_linux-run
./cuda_9.0.176.3_linux-run
./cuda_9.0.176.4_linux-run
cd cudnn-9.0-linux-x64-v7.4.1.5/cuda
cp include/cudnn.h /usr/local/cuda/include/
cp lib64/libcudnn* /usr/local/cuda/lib64/

cd
cp install_bak/apache2.conf /etc/apache2/apache2.conf
cp install_bak/ports.conf /etc/apache2/ports.conf
cp install_bak/000-default.conf /etc/apache2/sites-available/000-default.conf
cp install_bak/default-ssl.conf /etc/apache2/sites-available/default-ssl.conf
cp install_bak/php.ini /etc/php/7.2/apache2/php.ini
cp install_bak/proxychains.conf /etc/proxychains.conf
cp install_bak/hosts /etc/ansible/hosts
cp install_bak/sshd_config /etc/ssh/sshd_config
cp install_bak/openssl.py /usr/local/lib/python3.6/dist-packages/shadowsocks/crypto/openssl.py
service apache2 restart
service ssh restart

apt-mark hold linux-generic                        
apt-mark hold linux-headers-generic
apt-mark hold linux-image-generic  
apt-mark hold linux-signed-generic 
# apt install -y texlive-full wine64
```