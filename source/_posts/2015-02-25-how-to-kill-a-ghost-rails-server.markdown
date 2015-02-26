---
layout: post
title: "How to kill a ghost rails server"
date: 2015-02-25 22:37:34 -0800
comments: true
categories:
---
I've been working on a Rails-API for my latest project and I ran into a situation where my local server kept running even after I thought I had killed it. I had to figure out how to find the server running in the background and kill it with some sweet bash commands! I imagine I'll run into this problem again so I figured I'd right a quick post about how to do it.
<!-- more -->
The first step is to determine the PID of the ghost server. To do this enter the following command into your terminal:

```Bash
lsof -wni tcp:3000
```

If you use a different port other than 3000 for your Rails server simply change the above command to have your port number instead of 3000. This command should spit out something like this:

```Bash
COMMAND   PID USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
ruby    97750 Rich   11u  IPv6 0x96518f27a6f3295d      0t0  TCP [::1]:hbci (LISTEN)
ruby    97750 Rich   12u  IPv4 0x96518f27aa256e3d      0t0  TCP 127.0.0.1:hbci (LISTEN)
ruby    97750 Rich   13u  IPv6 0x96518f27a6f3251d      0t0  TCP [fe80:1::1]:hbci (LISTEN)
```

Take note of the PID. This is the 'process identifier' and we need it to kill our server. The last step is to enter the following command into your terminal:

```Bash
kill -9 [PID]
```

In my case, I would replace [PID] with 97750. That's all there is to it! Pretty simple once you know how.

(source: [stackoverflow](http://stackoverflow.com/questions/15088163/cant-stop-rails-server))