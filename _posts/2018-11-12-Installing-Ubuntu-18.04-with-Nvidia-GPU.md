---
layout: post
---

根据印象更新一下ubuntu安装过程

### 分区

50G给/，512M给boot，3G给swap，剩下给/home

然后会报错说什么引导会被修改，再给256M给efi就行

### 配环境

1. 修改 `/etc/apt/sources.list` 为tuna镜像源
2. 无线网络在Y7000P机子上会挂，应该是硬件问题，使用命令 `sudo modprobe -r ideapad_laptop` 即可启动
3. `sudo apt remove libreoffice* && sudo apt update && sudo apt upgrade && sudo apt autoremove`
4. 禁用nouveau：`sudo vim /etc/modprobe.d/blacklist.conf` 添加 `blacklist nouveau`；`sudo vim /etc/modprobe.d/blacklist-nouveau.conf` 添加
```bash
blacklist nouveau
blacklist lbm-nouveau
options nouveau modeset=0
alias nouveau off
alias lbm-nouveau off
```
然后 `sudo update-initramfs -u`
5. 安装驱动：`sudo ubuntu-drivers autoinstall`
6. `sudo add-apt-repository ppa:nilarimogard/webupd8; sudo apt install prime-indicator` 切换N卡
7. `sudo add-apt-repository ppa:linrunner/tlp; sudo apt install tlp` 自动调整频率省电
8. `sudo apt install git htop zsh vim tmux cmake curl axel texlive-full gummi proxychains python-pip python3-pip libopencv-dev libboost-dev gnome-tweak-tool openvpn openssl mpv wine64 xclip enca apache2 php7.2 unrar ruby gnome-shell-extensions dos2unix xserver-xorg-input-synaptics libinput-tools xdotool; sudo gem install fusuma` 并安装oh-my-zsh 和.tmux

```bash
# 如果是第一次
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
cd
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local .
# 如果装过了
chsh -s /usr/bin/tmux
```

5. 安装 chrome、typora、sublime、teamviewer、wps-office、sogoupinyin、vmware

6. 修改 `~/.pip/pip.conf` 然后 `sudo pip3 install pip torch torchvision opencv-python tensorflow-gpu jupyter matplotlib ipython --upgrade `

7. 同时安装macbuntu

```bash
sudo add-apt-repository ppa:noobslab/macbuntu
sudo apt-get update
sudo apt-get install macbuntu-os-icons-v1804 macbuntu-os-ithemes-v1804
```

7. 下载cuda9.0，选ubuntu16.04或者17.04版本的并安装，g++需要降级到g++-5之后再安装。下载5个run文件挨个执行。
```bash
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 10
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-5 10
```

8. 下载cudnn7.1.4匹配cuda9.0版本
```bash
sudo cp include/cudnn.h /usr/local/cuda/include/
sudo cp lib64/libcudnn* /usr/local/cuda/lib64/
```
安装之后在 `~/.zshrc` 中添加

```bash
export PATH=$PATH:/usr/local/cuda-9.0/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-9.0/lib64
```

10. `sudo vim /usr/local/lib/python3.6/dist-packages/shadowsocks/crypto/openssl.py` 改52和111行改成 `libcrypto.EVP_CIPHER_CTX_reset` 不然ss起不起来


### 效果图

![](/images/htop.png)

