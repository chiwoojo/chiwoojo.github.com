---
layout: post
title: Mac doesn't go to sleep with dual monitor set up. Solved. 
---

Does your Mac laptop not go to sleep when you shut it, only to run on the external display? Here is your solution. 

I came upon this problem myself, and after some Googling I found a solution that works. And I wanted to share with you all about it.

Open up your Terminal, and type

```bash
sudo nvram boot-args=iog=0x0
```

while external display is not connected and then reboot the computer. 

And that's it! 

Try it out :) 

Found this solution on [Superuser.](http://apple.stackexchange.com/questions/18037/why-wont-closing-the-lid-sleep-my-macbook-pro-with-external-monitor-attached-af)
