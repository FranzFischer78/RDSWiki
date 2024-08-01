---
description: >-
  RTCP stands for RaftTCP. We built our own networking layer to not rely on
  steam networking. Instead we rely on the TCP/IP technology to provide a stable
  and fast networking.
---

# Introducing RTCP (Our custom networking layer)

As said above, RTCP relies on the **TCP/IP(\*)** protocol, this allows us to provide dedicated servers without using Steam Networking and without being limited on the bandwidth etc..\
\
As we are using a different networking layer than the original game, **vanilla users(\*)** won't be able to join dedicated servers that uses this networking layer.\
\
As we don't rely on the steam services anymore, we needed a way to verify that users aren't using a pirated version and that they really own the account they are trying to join the server with.\
That's why when using RTCP you will need a [Steam Web API Key](https://steamcommunity.com/dev/apikey) which will allow your server to ask steam for authentication verification.\
\
Side Note : The steam API also have some benefits as it will allow you to reject users that are VAC banned, Publisher banned or users using family sharing.\


\* Vanilla Users : Users that are playing the original game without Raft Mod Loader.\
\
\* TCP/IP : (Transport Control Protocol) provides reliable data transmission service with end-to-end error detection and correction.
