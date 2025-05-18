---
title: Race Condition in chess
tags:
  - Bug Bounty
---

Recently I came back to Hackerone and found about lichess having a program in it, thought about how cool would be to hack something chess related like doing an extra move or something, sadly I wasnt able to find any direct cheat in the game but I was able to sneak a report nonetheless, a Race Condition that shows that they can be everywhere so lets dig in.

## Exploring the platform

Before even start to poke around chess games to find flaws I saw about teams being a feature in the platform so decided to create one to mess around and came across the following feature where the leader could message all the team at the same time, mind you the teams in lichess can have up to +500k members so its more of a guilds thing than teams per se, this message was restricted to only 7 messages per week maybe to avoid flooding from leaders? not sure but I quickly setted up burp.

![lichess-limit.png](https://ptyhokkaido.github.io/assets/images/lichess-limit.png)


## How to Race Condition with Burp

Clicking the send button and intercepting petition will do, send it to repeater and copy the request as many times as you want to send to the server, I had to change the body of the message for this ocassion otherwise wouldnt work.


![lichess-mssg-7.png](https://ptyhokkaido.github.io/assets/images/lichess-mssg-7.png)

![lichess-mssg-8.png](https://ptyhokkaido.github.io/assets/images/lichess-mssg-8.png)

Create a tag and save them all under the same tag, send them in parallel, profit.

![parallel.png](https://ptyhokkaido.github.io/assets/images/parallel.png)

This ends with my other account getting the inbox flooded by team messages.

![lichess-messages.png](https://ptyhokkaido.github.io/assets/images/lichess-messages.png)

## Mitigation

After reporting to lichess team they triaged it and pushed a fix with the following (sequencing the mongodb rate limiter).

https://github.com/lichess-org/lila/commit/76a76ddc41c9fc82daf8fa4dee3f2f20ae22f7da


## Take away

Race conditions are more common that what we think and can happen in so many scenarios you should always think of them, while this feature had a low impact many others could not be this lucky.



