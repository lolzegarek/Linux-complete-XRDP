# Complete config of XRDP on linux (in my case - fedora)

## Install xrdp 

```shell
sudo dnf install xrdp -y
```

Various Linux distribution may have diffrent install instructions, so you need to check out install tutorial for your distro.

## Disable suspend when laptop lid is closed

If you're using GNOME GUI you have to install **Tweaks** from *appstore*

![](img/appstore.png)

![](img/tweaks.png)

Disable 

```shell
sudo vi /etc/systemd/logind.conf
```

Find **HandleLidSwitch** and remove hash and change it to **ignore**

```shell
# /etc/systemd/logind.conf
HandleLidSwitch=ignore
```

Restart **systemd-logind**

```shell
sudo systemctl restart systemd-logind
```

