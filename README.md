---
description: >-
  RDS Stands for Raft Dedicated Server, it is a dedicated server project for the
  game Raft ! It includes TCP Networking, Anticheat, Plugins & more !
---

# Introducing RDS

{% hint style="warning" %}
RDS is currently in Alpha and only available for our patrons above 5$, If you want to host your own server until we get out of the alpha, visit [our patreon page](https://www.patreon.com/hytekgames) and get yourself a key by supporting us to download RDS.
{% endhint %}

RDS is an application that will manage your raft installation to run 24/7 with no interruptions.\
\
Like our Mod Loader, RDS will allow you to install plugins on your server to allow you to have **minigames**, **pvp arenas**, **ranks/permissions**, **chat commands**, **world protection** & anything you can think about !

\
RDS has 2 networking layers, RTCP and Steam.

*   RTCP will use TCP/IP protocol and won't require a 2nd Raft copy.

    Note : When using RTCP, steam services are disabled to redirect all the traffic to your server, this means that **vanilla users(\*)** without our mod loader won't be able to join the server.
* Steam will use Raft original networking and will require a 2nd Raft copy. (It is also quite glitchy since it requires Steam)

As you may know, Raft is mostly **client authoritative(\*)** so we are hardly working on making it more secure by going towards a **server authoritative(\*)** solution but that will be in the far future since it is a lot of work to redo most of the raft networking.&#x20;

In order to currently fight against cheaters, we made a small Anticheat (Thanks to Aidanamite) It will track most known things that we can tracked such as dealing more damages than what you can do, trying to detect if you go too fast, preventing cheaters from dropping cheated items etc. Please note that it is not perfect and will most likely have false positives and won't catch every cheater.

\
\* Vanilla Users : Users that are playing the original game without Raft Mod Loader.\
\
\* Client Authoritative : This means that almost nothing is verified by the server, like your inventory isn't verified by the server so the players can cheat as they like, same for the position etc.

\* Server Authoritative : This means that most things will be verified OR managed by the server, for example your inventory will entirely be on the server and it will tell you what you have in it, so you have NO WAY of cheating, same for your position, the server will do the same moves as you and detect if there's some cheat going on.

{% hint style="danger" %}
Hosting a RDS server will require you to own a legal Raft copy on Steam.

**RDS IS NOT SUPPORTING PIRATED/CRACKED VERSIONS.**
{% endhint %}
