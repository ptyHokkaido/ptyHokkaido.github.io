---
title: Why did I fail my OSCP
tags:
  
---

As the title says, I failed my OSCP exam few days ago and wanted to type down my mistakes for my future self and whoever read this article so hopefully it can help.

## Preparation

I did all the machines of their labs apart of Skylark in a month, followed by the already famous Lain Kusanagi OSCP like excel, since I did recommended Proving Grounds machines long ago and still had some of its writeups I looked for other sources to learn, here is where HTB Academy came up, got AD enumeration and Windows privesc modules since I felt those were my weaknesses and nowdays 80% of OSCP its Windows, do NOT overlook Windows please.

HTB Academy was huge and gave me confidence and tools for my methodology, wanting to use those together I hopped on recommended VulnLab machines and this is by far the most realistic machines I've done, after getting my OSCP (since for this certification most of their machines are overkill) I'll stick to this platform since the amount of stuff you learn for actual pentests are incredible. Did few of Windows and AD recommended machines.

Of course previous to all of this I did most of recommended AD + Windows machines on HTB.

Since I still had week and a half till my scheduled exam I decided to refresh stuff on Linux so went for a Virtual Hacking Labs subscription, after reading of it on Reddit and such I decided to give it a try, personally dont think was worth the investment, most of Linux boxes were outdated and tried three Windows machines which ended up being Windows XPs... all in all learnt few stuff which I'd probably recommend if the subscription was 20€ or something but definetenly NOT 100€ whichs its current price. Ended up doing around 14 machines in that span of time.


## Exam

I believe I got the AD nightmare set whichs not an excuse. I couldnt get a foothold after trying everything, not by AD services neither Web apps, nothing worked. A tip on this would be do training and research about enumerating the AD from inside, what does this mean? all the info you could get through external tools such as domain users, domain groups, etc should be accesible from the account OffSec gives you in this new format exam.

Standalones, after many hours I over enumerated certain services leaving others with minimum enumeration. It was till 10h later that I found out one of the commands I did at the beginning of my recon should have worked out but it didnt work as it should have, making me go through overthinking stuff for the next 10h hours. Was it my fault? It kinda was, I should have repeated that command multiple times to make sure output was right, I should have restarted my recon from the beginning way earlier since for some reason it wasnt working, I was missing pieces of information everywhere.

After getting the correct output from those services I got foothold in one of them and pwned another but it was just too late for me and I was already tired.


## Take away

1. Dont overcomplicate it, OSCP is still an entry certification. if you feel you're going too deep and nothing works, go back to the beginning, you missed out on initial information.
2. Try to learn your AD enumeration from inside and add it to the toolbelt, with the new format we've an account in the domain, it'll most likely speed up your enumeration.
3. Rest and again dont overcomplicate stuff.

Till this days I've no idea about the foothold on that AD, as is when I start thinking about it I dont really think I missed on enumeration neither got new ideas to try. I'll wait for my cooldown period, gonna try and get Zephyr in the meantime although its overkill but at least it'll help me to not getting rusty in AD and get more comfy on it.
