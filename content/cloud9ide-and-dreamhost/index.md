---
title: "Cloud9IDE and Dreamhost"
description: "Since I like to grab whatever computer I can find closest to me, the idea of my work being in the cloud obviously sounds very appealing…"
date: "2013-08-02T00:00:00.000Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/cloud9ide-and-dreamhost-1b36fa6f073
redirect_from:
  - /cloud9ide-and-dreamhost-1b36fa6f073
---

Cloud9IDE and Dreamhost

Since I like to grab whatever computer I can find closest to me, the idea of my work being in the cloud obviously sounds very appealing. Yesterday I decided to make the ultimate jump and move my development environment to the cloud too. Enter [Cloud9 IDE](https://c9.io/). It really is like Google Docs for code. Read up on it yourself, but here’s how i got my shared Dreamhost account to play nice.

### How

I warn you, i think using node.js to actually build production applications is a violation of Dreamhost TOS, but hopefully they’ll turn a blind-eye to this for our purposes. Still, i take no responsibility for what happens next.  
 First get node.js:

```
cd ~ #go to your home directory
mkdir usr/local/bin #make a local bin
mkdir tmp #make a new directory called tmp cd tmp #cd into tmp
git clone https://github.com/joyent/node.git #clone node.js
cd node #cd into node git checkout v0.10.15 # v0.10.xx being required at the time i write this
./configure --prefix=$HOME/usr/local #configure it for your local directory
# ... random configuration text ...
make #make it
# ... random compile text ...
make install #make install it
# ... more random text ...
echo 'export PATH=$PATH:/home/[YOURUSERNAME]/usr/local/bin' >> .bashrc #replace [YOURUSERNAME] with your user
echo 'export PATH=$PATH:/home/[YOURUSERNAME]/usr/local/bin' >> .bash_profile #replace [YOURUSERNAME] with your user

#now logout and log back in
```

Now start creating a new workspace on Cloud9 IDE and select _SSH_ for Hosting. Copy the rsa key and run the following command on your Dreamhost server:

```
echo 'PASTE RSA KEY HERE' >> ~/.ssh/authorized_keys
```

Now fill out the host and username, test connection and because it says successful, go do your thing.

**Cloud9IDE and Dreamhost** was published on August 02, 2013.

---

_Originally published at_ [_//amin.gilani.me/geeking-out/2013/08/02/cloud9ide-and-dreamhost/_](//amin.gilani.me/geeking-out/2013/08/02/cloud9ide-and-dreamhost/) _on August 2, 2013._
