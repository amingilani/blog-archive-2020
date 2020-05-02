---
title: "Please use git"
description: "Despite it being 2016+, and Git being ubiquitous among organizations and teams, I’ve met a surprising number of people in Pakistan that…"
date: "2016-10-12T21:32:00.513Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/please-use-git-da3bea7d1234
redirect_from:
  - /please-use-git-da3bea7d1234
---

![](./asset-1.png)

Despite it being 2016+, and Git being ubiquitous among organizations and teams, I’ve met a surprising number of people in Pakistan that don’t use version control. It makes it incredibly difficult for me to collaborate with them.

Even if you’re not from Pakistan, and you don’t use a Version Control System (VCS) like Git, you should. I can’t believe I have to explain this, but when combined with a code hosting site like Github, or Gitlab, or Bitbucket, you get:

-   A complete project history
-   Proper versioning
-   Restoring to a previous version
-   The ability to collaborate efficiently
-   Automated backups
-   The ability to hook on automated build services
-   A better view of your changes in realtime
-   A better view of your code evolution over time

This piece (rant) points out some of the excuses I get from people for not using git, and explains why they’re not good excuses.

> It’s too complicated

No it isn’t. Like any other technology, you need to spend a little time learning it, and integrating it in your workflow, but once that’s done: **you’ll probably only use about ten commands — ever.** Read [Sam Corcos](https://medium.com/u/202fbe17df40)’ [article](https://medium.freecodecamp.com/git-cheat-sheet-and-best-practices-c6ce5321f52) because those are all the commands I use.

> I’m not too good with the command line.

Does the black and white text screen scare you? It shouldn’t, [don’t be scared of the command](http://www.howtogeek.com/138675/htg-explains-why-you-shouldnt-be-scared-of-the-terminal-on-linux/) line. As a developer you’re going to have to learn it at some point or hamper your development by using GUI apps as a crutch when the alternative would be so much more efficient.

If you’re still not convinced, here’s a list of some very good cross platform Git clients that have beautiful interfaces:

-   [GitKraken](https://www.gitkraken.com/)
-   [Github Desktop](http://desktop.github.com/)
-   [Any of these](https://git-scm.com/downloads/guis)

> “Our project is too small”

There’s no such thing. Even if your project is ten lines of codes long, it serves a purpose, and should be version controlled. With a VCS, you get:

-   The ability to publish your project
-   Attract contributors
-   Make future project growth a possibility
-   A timeline of all your changes
-   The ability to undo changes
-   Backups for your repository with **one** command
-   Synchronized codebase across all your devices

You also get:

-   The ability to automatically deploy your code to the servers
-   Automatic tests for every single code change

> “Our team is too small”

There’s no such thing. Even with one person, you get:

-   A timeline of all your changes
-   The ability to undo changes
-   Backups for your repository with **one** command
-   Synchronized codebase across all your devices

With two people or more, you get:

-   Code sharing with **one** command
-   A single source of the latest codebase
-   An eagle-eye view of all the codebase changes
-   Accountability on code contributions
-   Statistics on individual contributors
-   Streamlined code-review

> “We use Dropbox”

That is not an answer. Dropbox is meant for file storage and sharing. It isn’t as efficient as git for code sharing, and it doesn’t help with conflicts. Oh, you use file history to revert back to older versions? Still not good enough. It doesn’t go further than thirty days. You know what has great version history? a VCS. Guess what isn’t a VCS. Dropbox.

> “We use email attachments”

-   How many versions of your codebase do you have?
-   How many times has your code split into multiple branches because people didn’t copy other people’s changes before working on their own?
-   Do you like copying and pasting each other’s code into your own?

By the way, Git supports email collaboration through [patches](https://git-scm.com/book/en/v2/Git-Commands-Patching). In fact, emailed git patches are the preferred way to [submit patches to the Linux kernel](https://www.kernel.org/doc/Documentation/SubmittingPatches).

> “Our designers aren’t technical”

Do your designers create HTML and CSS files? They’re technical enough to be using Git. What’s amazing is that with the help of Github pages, you can view their [latest changes](https://pages.github.com/) by visiting a url in your browser.

Our [company website](https://payload.tech/) is hosted on Github pages. It’s just HTML/CSS in a [git repository](https://github.com/payloadtech/corporate-site).

> “I’m a student”

You need it the most! When you’re a student you tackle code challenges every day. Without a VCS to help you backup your code, you’ll eventually lose it to a hard disk failure, or broken USB drive, and lose all your past knowledge.

Also, on Github, you get to show off your portfolio. As an employer which would you choose:

-   Adam: his resume says he wrote an amazing calendar app for a school project.
-   Bob: his resume says he wrote an amazing calendar app for a school project, **and he has a link to review his code on Github**.

> “I don’t need a VCS”

[You do.](https://www.git-tower.com/learn/git/ebook/en/mac/basics/why-use-version-control)

> “No I don’t”

[Yes](http://stackoverflow.com/questions/1408450/why-should-i-use-version-control) [you](http://soundsoftware.ac.uk/why-version-control) [fucking](http://oss-watch.ac.uk/resources/versioncontrol) [do](https://www.quora.com/What-is-git-and-why-should-I-use-it).

> “I have large dependency files”

Git has the ability to [ignore specified files in your repositories](https://git-scm.com/docs/gitignore). Use a [build system](https://en.wikipedia.org/wiki/Build_automation) to fetch and install your dependencies, and don’t check them into your code. Here’s [a list of tools](https://en.wikipedia.org/wiki/List_of_build_automation_software) you could use.

> “I have large files and datasets that need to be stored in the code”

[Git LFS has you covered.](https://git-lfs.github.com/)

> I don’t want people to see my code.

-   Does your code embarrass you? It shouldn’t, we all started from writing shitty code. [I know I did](https://github.com/payloadtech/mailpenny/blob/c2768f59b97f431789f754ddac21b396d0cbe6bd/routes/api.js).
-   Is your code private and confidential? It probably isn’t, but if it is, [Gitlab](https://about.gitlab.com/) and [Bitbucket](https://bitbucket.org/) let you host unlimited private repositories for free.

> I prefer X instead of Git

Blasphemy.

On a serious note: despite X being a personal choice, Git is the popular choice. Using Git instead of X will make it easier for people to jump onboard quickly! If you want to reach as many collaborators as possibly, Github is definitely the way to go.

That aside, I also use spaces instead of tabs, and I use Atom over Vim, Emacs, and Sublime. If you’d like to start a flame war, you’re welcome to tweet at me. 😉

---

If you have other reasons for not using Git, please tweet at me and I’ll add them here with a response.

Share this with your boss, **teacher**, team lead, or that weird friend who refuses to listen to you, to get them to create a saner workflow.

Also, if you like pre-launch software, check out my app at [Mailpenny.com](https://mailpenny.com), it’s open source and hosted on [github](https://github.com/payloadtech/mailpenny):

-   The `master` branch automatically deploys to production
-   Every push automatically [runs tests](https://travis-ci.org/payloadtech/mailpenny)
-   Every push runs [coverage tests](https://coveralls.io/github/payloadtech/mailpenny?branch=dev)
-   Every push compiles and [publishes documentation](http://www.rubydoc.info/github/payloadtech/mailpenny/dev)
-   Every Github push, deploy, issue, or pull request notifies me [on Slack](https://github.com/integrations/slack)

[![](./asset-2.png)](http://bit.ly/HackernoonFB)[![](./asset-3.png)](https://goo.gl/k7XYbx)[![](./asset-4.png)](https://goo.gl/4ofytp)

> [Hacker Noon](http://bit.ly/Hackernoon) is how hackers start their afternoons. We’re a part of the [@AMI](http://bit.ly/atAMIatAMI) family. We are now [accepting submissions](http://bit.ly/hackernoonsubmission) and happy to [discuss advertising & sponsorship](mailto:partners@amipublications.com) opportunities.

> If you enjoyed this story, we recommend reading our [latest tech stories](http://bit.ly/hackernoonlatestt) and [trending tech stories](https://hackernoon.com/trending). Until next time, don’t take the realities of the world for granted!

[![](./asset-5.jpeg)](https://goo.gl/Ahtev1)
