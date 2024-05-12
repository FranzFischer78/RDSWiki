---
description: >-
  Installing a Raft Dedicated Server on Linux is a bit more complicated than
  Windows but if you have some basic knowledge of linux you can probably do it.
---

# Debian based GUI Distro : Installing your server

<figure><img src="../../.gitbook/assets/linux.png" alt=""><figcaption></figcaption></figure>

RDS is really easy to install as it is a single application named **RaftDedicatedServer.exe** that you can download on our master website available [here](https://master.raftmodding.com/).

{% hint style="warning" %}
This tutorial has been written for Ubuntu 22.04 LTS.\
It should work on other debian based linux distributions. When it comes to other distro families like Redhat, Arch, ... you will need to adapt the commands.
{% endhint %}

### How to install ?

There's two ways to install RDS on linux, you can either use our automated script or follow our step by step tutorial.\
\
If you don't really know what you are doing, we recommend you to use our automated script.

{% tabs %}
{% tab title="Automated Script" %}
1 ) Download our bash script from [here](https://fastdl.raftmodding.com/installrds.sh).\
\
2 ) Put in your home/YOUR\_USER folder.\
\
3 ) Run the command `chmod 777 ./installrds.sh`

4 ) Launch the installation with `./installrds.sh`\
\
5 ) Create a folder for your server.\
\
6 ) Now, the patching part of RDS isn't working yet on linux, so you need to install it first on windows and then everything will work fine. So download RDS from [here](https://master.raftmodding.com/download) and follow the Windows guide to get it running on windows.\
\
7 ) Upload your entire server directory from your windows installation to your server folder on linux.\
\
8 ) Now to run your server go in your server folder with `cd yourserverfolder` and use the following command.\
`/usr/bin/xvfb-run -a -l env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
8 ) Now that your server "should" be working, in order to let it run 24/7 when you close the terminal, you can use **screen** with the commands below.\
\
Launching the server :\
`screen -R RDS /usr/bin/xvfb-run -l -a env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
To get back in the server window after logging back in into your VPS, type `screen -r`\
To leave your server window without killing it press `CTRL+A+D`
{% endtab %}

{% tab title="Step by step with commands" %}
1 ) Make sure your distribution is up to date.\
Run the command `sudo apt update` to update all your packages.\
\
2 ) Installing the required dependencies.\
In order to run the RaftDedicatedServer.exe file on linux, you'll need to install some third party softwares on your linux server such as [Wine](https://www.winehq.org/) & [Mono](https://www.mono-project.com/).\
Run `sudo apt install -y winetricks xvfb` to install wine.\
Run `wget https://dl.winehq.org/wine/wine-mono/5.0.0/wine-mono-5.0.0-x86.msi` to download mono for wine.\
Run `msiexec /i wine-mono-5.0.0-x86.msi` to install mono for wine.\
Run `sudo winetricks dotnet46` to install .NET 4.6 for wine.

3 ) Configuring winetricks\
Winetricks need to be configured else it'll output many errors when running the server.\
Simply run `sudo winetricks sound=disabled` to disable ALSA sound library from wine.\
\
4 ) Create a folder for your server.\
\
5 ) Now, the patching part of RDS isn't working yet on linux, so you need to install it first on windows and then everything will work fine. So download RDS from [here](https://master.raftmodding.com/download) and follow the Windows guide to get it running on windows.\
\
6 ) Upload your entire server directory from your windows installation to your server folder on linux.\
\
7 ) Now to run your server go in your server folder with `cd yourserverfolder` and use the following command.\
`/usr/bin/xvfb-run -a -l env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
8 ) Now that your server "should" be working, in order to let it run 24/7 when you close the terminal, you can use **screen** with the commands below.\
\
Launching the server :\
`screen -R RDS /usr/bin/xvfb-run -l -a env WINEDLLOVERRIDES="winhttp.dll=n,b" env WINEDEBUG="-all" wine64 RaftDedicatedServer.exe`\
\
To get back in the server window after logging back in into your VPS, type `screen -r`\
To leave your server window without killing it press `CTRL+A+D`
{% endtab %}
{% endtabs %}
