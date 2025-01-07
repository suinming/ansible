# ansible

my ansible scripts for different operating system

# Linux

- ubuntu24.04

## Install process

1. generate SSH key and add the key to GitHub

```shell
ssh-keygen -t ed25519
```

2. install git, ansible, `KeepassXC`

```shell
sudo apt install git ansible keepassxc
```

3. clone the ansible repository from GitHub by using SSH

```shell
git clone git@github.com:suinming/ansible.git
```

4. execute the ansible playbook

need to add the extra-vars argument to specific Linux version

```shell
ansible-playbook -i inventory main_ubuntu24.04.yml --ask-become-pass
```

> [!WARNING]  
> ubuntu24.04的firefox使用snap下載，會有無法輸入中文的問題
> 使用官方的作法，從 APT 倉庫安裝 .deb 套件包[doc_link](https://support.mozilla.org/zh-TW/kb/install-firefox-linux?utm_source=www.mozilla.org&utm_medium=referral&utm_campaign=firefox-download-thanks&_gl=1*9q6f4w*_ga*MjczMTI3MTg2LjE3MzU3MTgxNzg.*_ga_MQ7767QQQW*MTczNTcxODE4NC4xLjEuMTczNTcxODE5My4wLjAuMA..#w_install-firefox-deb-package-for-debian-based-distributions)

# Win10 subsystem for Linux

## Install process

1. install `KeepassXC` from the browser

> [!WARNING]  
> I am getting "System Error: VCRUNTIME140_1.dll was not found" when starting KeePassXC. Why?
> This error indicates that you are missing the MSVC runtime library (Microsoft Visual C++ Redistributable). You can download the latest version from Microsoft [download link](https://aka.ms/vs/17/release/vc_redist.x64.exe).

2. install windows subsystem Linux

```shell
wsl --install
```

3. install window terminal in Microsoft Store

4. generate SSH key and add the key to GitHub

```shell
ssh-keygen -t ed25519
```

5. clone the ansible repository from GitHub by using SSH

```shell
git clone git@github.com:suinming/ansible.git
```

6. setup `SpaceMono Nerd Font` in window

- download [SpaceMono Nerd Font](https://www.nerdfonts.com/font-downloads)
- go to download directory select all the SpaceMono Nerd Font and right click to install
- ubuntu > 其他設定 > 外觀 > 字體(選擇 SpaceMonoe)
- in window terminal settings>settings.json and change the profiles section in the json

```json
    "profiles":
    {
        "defaults": {
          "font": {
            "face": "SpaceMono Nerd Font"
          }
        },
    }
```

7. install ansible

```shell
sudo apt install ansible
```

8. execute the ansible playbook

```shell
ansible-playbook ./ansible/w10.yml --ask-become-pass
```
