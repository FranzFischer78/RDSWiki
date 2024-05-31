---
description: >-
  Installing a Raft Dedicated Server on Linux is a bit more complicated than
  Windows but if you have some basic knowledge of linux you can probably do it.
---

# CLI based Distro: Installing your server

<figure><img src="../../.gitbook/assets/linux.png" alt=""><figcaption></figcaption></figure>

RDS is really easy to install as it is a single application named **RaftDedicatedServer.exe** that you can download on our master website available [here](https://master.raftmodding.com/).

{% hint style="warning" %}
This tutorial has been written for Ubuntu Server 22.04 LTS.\
It should work on most other debian based linux distributions. When it comes to other distro families like Redhat, Arch, ... you will need to adapt the commands.

This guide is for Distros that only have a command line interface. If your distro does provide a user interface you should [check the other guide](linux-installing-your-server.md).&#x20;
{% endhint %}

### How to install ?

There's two ways to install RDS on linux, you can either use our automated script or follow our step by step tutorial.\
\
If you don't really know what you are doing, we recommend you to use our automated script.

{% tabs %}
{% tab title="Automated Script" %}
1 ) Upload all the Raft game files onto your server.

2\) Download RDS from [here](https://master.raftmodding.com/download) and put it into your server directory.

3\) CD into your RDS directory&#x20;

4\) [Download our bash script](https://fastdl.raftmodding.com/installrdsscript.sh) into your RDS directory.\
( `wget`[`https://fastdl.raftmodding.com/installrdsscript.sh`](https://fastdl.raftmodding.com/installrdsscript.sh) )\
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
4 ) Upload all the Raft game files onto your server.\
\
5 ) Download RDS from [here](https://master.raftmodding.com/download) and put it into your server directory.\
\
6 ) Now to run your server go in your server folder with `cd yourserverfolder` and use the following command.\
`sudo /usr/bin/xvfb-run -a -l env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
7 ) Now that your server "should" be working, in order to let it run 24/7 when you close the terminal, you can use **tmux** with the commands below.

Launching the server :\
`sudo tmux new-session -d -s RDS 'sudo /usr/bin/xvfb-run -l -a env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe'`\
\
Connect to the tmux session:\
`sudo tmux attach-session -t RDS`\
\
To leave your tmux session without killing it press `CTRL+B` then `D`

Heres  a useful cheatsheet if you need help with tmux: [https://tmuxcheatsheet.com/](https://tmuxcheatsheet.com/)
{% endtab %}
{% endtabs %}
