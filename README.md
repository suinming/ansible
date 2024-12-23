# ansible

my ansible script for different OS

# ubuntu_24.04_LTS

1. generate ssh key and add the key to github

```shell
ssh-keygen -t ed25519
```

2. install git, ansible, keepassxc

```shell
sudo apt install git ansible keepassxc
```

3. clone the ansible repo from github by using SSH

```shell
git clone git@github.com:suinming/ansible.git
```

4. execute the ansible playbook

```shell
ansible-playbook ./ansible/ubuntu24.04.1.yml --ask-become-pass
```

# win10_wsl

1. install keepassxc from the browser

> [!WARNING]  
> I am getting "System Error: VCRUNTIME140_1.dll was not found" when starting KeePassXC. Why?
> This error indicates that you are missing the MSVC runtime library (Microsoft Visual C++ Redistributable). You can download the latest version from Microsoft [download link](https://aka.ms/vs/17/release/vc_redist.x64.exe).

2. install wsl

```shell
wsl --install
```

3. install window terminal in Microsoft Store

4. generate ssh key and add the key to github

```shell
ssh-keygen -t ed25519
```

5. clone the ansible repo from github by using SSH

```shell
git clone git@github.com:suinming/ansible.git
```

6. setup SpaceMono Nerd Font in window

- download [SpaceMono Nerd Font](https://www.nerdfonts.com/font-downloads)
- go to download directory select all the SpaceMono Nerd Font and right click to install
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
