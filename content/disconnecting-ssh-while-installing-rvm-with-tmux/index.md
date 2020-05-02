---
title: "Disconnecting SSH while installing rvm, with TMUX"
description: "I just discovered tmux. Until recently I used to stay connected to my machines with ssh while I was running upgrades, but now I can just…"
date: "2016-09-26T07:42:20.261Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/disconnecting-ssh-while-installing-rvm-with-tmux-a6123c052b16
redirect_from:
  - /disconnecting-ssh-while-installing-rvm-with-tmux-a6123c052b16
---

I just discovered tmux. Until recently I used to stay connected to my machines with ssh while I was running upgrades, but now I can just run them, disconnect, and check up on them later.

Prerequisites: Install `tmux` on the remote host

Here’s how I installed `rvm` on my RaspberryPi:

1.  Connect via ssh: `ssh pi@rasbperrypi`
2.  Open a tmux session called rvm: `tmux new -s rvm`
3.  Run the rails installer `\curl -sSL [https://get.rvm.io](https://get.rvm.io) | bash -s stable — rails`
4.  Detach from the session `ctrl + b` and `d`
5.  Disconnect from ssh if you’d like
6.  Later on, connect back to ssh, and get back into the tmux session with `tmux a`
