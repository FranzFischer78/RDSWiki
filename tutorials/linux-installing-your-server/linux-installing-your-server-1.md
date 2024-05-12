---
description: >-
  Installing a Raft Dedicated Server on Linux is a bit more complicated than
  Windows but if you have some basic knowledge of linux you can probably do it.
---

# Debian based CLI Distro : Installing your server

<figure><img src="../../.gitbook/assets/linux.png" alt=""><figcaption></figcaption></figure>

RDS is really easy to install as it is a single application named **RaftDedicatedServer.exe** that you can download on our master website available [here](https://master.raftmodding.com/).

{% hint style="warning" %}
This tutorial has been written for Ubuntu Server 22.04 LTS.\
It should work on other debian based linux distributions. When it comes to other distro's like Redhat, Arch, ... based ones you will need to adapt the commands.
{% endhint %}

### How to install ?

There's two ways to install RDS on linux, you can either use our automated script or follow our step by step tutorial.\
\
If you don't really know what you are doing, we recommend you to use our automated script.

{% tabs %}
{% tab title="Automated Script" %}
1 )  The patching part of RDS isn't working yet on linux, so you need to install it first on windows and then everything will work fine. So download RDS from [here](https://master.raftmodding.com/download) and follow the Windows guide to get it running on windows.

2\) Upload your entire server directory from your windows installation to a folder for RDS on your linux server.

3\) CD into your RDS directory&#x20;

4\) Download our bash script into your RDS directory.\
\
5 ) Run the command `sudo chmod +rwx ./installrdsscript.sh`

6 ) Launch the installation with `sudo ./installrdsscript.sh`\
\
7 ) Now to run your server execute the following command `sudo ./launchrds.sh`\
\
8 ) Now that your server "should" be working, in order to let it run 24/7 when you close the terminal, you can use **tmux** with the commands below.\
\
Launching the server :\
`sudo tmux new-session -d -s RDS 'sudo ./launchrds.sh'`

Connect to the tmux session:\
`sudo tmux attach-session -t RDS`\
\
To leave your tmux session without killing it press `CTRL+B` then `D`

Heres  a useful cheatsheet if you need help with tmux: [https://tmuxcheatsheet.com/](https://tmuxcheatsheet.com/)
{% endtab %}

{% tab title="Step by step with commands" %}
1 ) Make sure your distribution is up to date.\
Run the command `sudo apt update` to update all your packages.\
\
2 ) Installing the required dependencies.\
In order to run the RaftDedicatedServer.exe file on linux, you'll need to install some third party softwares on your linux server such as [Wine](https://www.winehq.org/) & [Mono](https://www.mono-project.com/).\
Run `sudo apt install -y winetricks xvfb` to install wine.\
Run `sudo dpkg --add-architecture i386` to allow us to download 32 bit packages\
Run the command `sudo apt update` to get the 32 bit package registry.\
Run `sudo apt install -y wine32` to install wine32\
Run `wget https://dl.winehq.org/wine/wine-mono/5.0.0/wine-mono-5.0.0-x86.msi` to download mono for wine.\
Run `msiexec /i wine-mono-5.0.0-x86.msi` to install mono for wine.\
\
3 ) Create a folder for your server.\
\
4 ) Now, the patching part of RDS isn't working yet on linux, so you need to install it first on windows and then everything will work fine. So download RDS from [here](https://master.raftmodding.com/download) and follow the Windows guide to get it running on windows.\
\
5 ) Upload your entire server directory from your windows installation to your server folder on linux.\
\
6 ) Now to run your server go in your server folder with `cd yourserverfolder` and use the following command.\
`sudo /usr/bin/xvfb-run -a -l env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
7 ) Now that your server "should" be working, in order to let it run 24/7 when you close the terminal, you can use **tmux** with the commands below.\
\
Launching the server :\
`screen -R RDS /usr/bin/xvfb-run -l -a env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
To get back in the server window after logging back in into your VPS, type `screen -r`\
To leave your server window without killing it press `CTRL+A+D`
{% endtab %}
{% endtabs %}
