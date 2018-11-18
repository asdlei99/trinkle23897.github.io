---
layout: post
---

根据印象更新一下ubuntu安装过程

### 分区

50G给/，256M给boot，3G给swap，剩下给/home

然后会报错说什么引导会被修改，再给256M给efi就行

### 配环境

1. 修改 `/etc/apt/sources.list` 为tuna镜像源

2. 无线网络在Y7000P机子上会挂，应该是硬件问题，使用命令 `sudo modprobe -r ideapad_laptop` 即可启动

3. `sudo apt update && sudo apt upgrade`

4. `sudo apt install git htop zsh vim tmux cmake curl axel texlive-full gummi proxychains python-pip python3-pip libopencv-dev libboost-dev gnome-tweak-tool openvpn openssl mpv wine64 xclip enca apache2 php7.2 unrar` 并安装oh-my-zsh 和.tmux

```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
cd
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local .
```

5. `sudo apt remove libreoffice* && sudo apt autoremove`，之后安装 chrome、typora、sublime、teamviewer、wps-office、sogoupinyin、vmware

6. 修改 `~/.pip/pip.conf` 然后 `sudo pip3 install pip torch torchvision opencv-python tensorflow-gpu jupyter matplotlib ipython --upgrade `

7. 同时安装macbuntu

```bash
sudo add-apt-repository ppa:noobslab/macbuntu
sudo apt-get update
sudo apt-get install macbuntu-os-icons-v1804 macbuntu-os-ithemes-v1804
```

7. 装目前最新的nvidia驱动，现在是410，可是ubuntu软件源只有390

8. 下载cuda9.0，选ubuntu17.04版本的并安装，g++需要降级到g++-5，`sudo update-alternatives --config gcc`

9. 下载cudnn7.1.4匹配cuda9.0版本的，安装之后在 `~/.zshrc` 中添加

   ```bash
   export PATH=$PATH:/usr/local/cuda-9.0/bin
   export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-9.0/lib64
   ```

10. 关盖子再开起来会花屏，解决方案是 `sudo vim /etc/default/grub` 把 `quiet splash ` 改成 `text`

11. `sudo vim /usr/local/lib/python3.6/dist-packages/shadowsocks/crypto/openssl.py` 改52和111行改成 `libcrypto.EVP_CIPHER_CTX_reset` 不然ss起不起来

12. 可以使用命令 `sudo prime-select intel|nvidia` 选择要使用的显卡来省电|炼丹，重启生效

### 效果图

![](/images/htop.png)

