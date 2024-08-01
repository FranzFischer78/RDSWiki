---
description: >-
  We present RaftDedicatedServer (RDS) – Easily run your Raft world 24/7. Rent a
  server from BisectHosting or self-hostable for our patrons above $5, RDS
  offers an unparalleled experience.
---

# Introducing Raft Dedicated Servers

{% hint style="info" %}
If you want to self-host your server you can do so by becoming a +5$ patron on our [patreon page](https://www.patreon.com/hytekgames), but keep in mind that self-hosting the software on linux can be challenging, However we've got guides to help you out :)
{% endhint %}

<figure><img src=".gitbook/assets/bisect_horizontal.jpg" alt=""><figcaption><p>Easily rent a server from <a href="https://www.bisecthosting.com/raft?r=rdswiki">BisectHosting</a> and get your raft world running within seconds with a one click installation !</p></figcaption></figure>

{% hint style="info" %}
Rent a server from [BisectHosting](https://www.bisecthosting.com/raft?r=rdswiki) to get your server running within minutes! With their optimized panel, you can manage online players, schedule tasks, easily install plugins, and more.

[BisectHosting](https://www.bisecthosting.com/raft?r=rdswiki) offers the best experience for hosting your Raft dedicated server!
{% endhint %}

RDS is an application that will manage your raft installation to run 24/7 with no interruptions.\
\
Like our Mod Loader, RDS will allow you to install plugins on your server to allow you to have **minigames**, **pvp arenas**, **ranks/permissions**, **chat commands**, **world protection** & anything you can think about !

\
RDS has 2 networking layers, RTCP and Steam.

*   RTCP will use TCP/IP protocol and won't require a 2nd Raft copy.

    Note : When using RTCP, steam services are disabled to redirect all the traffic to your server, this means that **vanilla users(\*)** without our mod loader won't be able to join the server.
* Steam will use Raft original networking and will require a 2nd Raft copy.\
  _**If you rent a**_ [_**BisectHosting**_](https://www.bisecthosting.com/raft?r=rdswiki) _**server you can directly input your 2nd raft account on their panel and make your server available to vanilla users within minutes!**_

As you may know, Raft is mostly **client authoritative(\*)** so we are hardly working on making it more secure by going towards a **server authoritative(\*)** solution but that will be in the far future since it is a lot of work to redo most of the raft networking.&#x20;

In order to currently fight against cheaters, we made a small Anticheat (Thanks to Aidanamite) It will track most known things that we can tracked such as dealing more damages than what you can do, trying to detect if you go too fast, preventing cheaters from dropping cheated items etc. Please note that it is not perfect and will most likely have false positives and won't catch every cheater.

\
\* Vanilla Users : Users that are playing the original game without Raft Mod Loader.\
\
\* Client Authoritative : This means that almost nothing is verified by the server, like your inventory isn't verified by the server so the players can cheat as they like, same for the position etc.

\* Server Authoritative : This means that most things will be verified OR managed by the server, for example your inventory will entirely be on the server and it will tell you what you have in it, so you have NO WAY of cheating, same for your position, the server will do the same moves as you and detect if there's some cheat going on.
