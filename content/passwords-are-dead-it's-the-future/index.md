---
title: "Passwords are dead. It’s the future"
description: "Hey, my boss said to talk to you — I hear you know a lot about web authentication?"
date: "2016-09-30T16:23:26.325Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/passwords-are-dead-its-the-future-e3e95affd9a6
redirect_from:
  - /passwords-are-dead-its-the-future-e3e95affd9a6
---

Hey, my boss said to talk to you — I hear you know a lot about web authentication?

_\-Yeah, I’m more of a passwordless authentication guy now. With cryptography being where it is right now, it’s hilarious how we used human memory for password authentication. I’m excited about how we can use SQRL and the_ [_blockchain_](https://hackernoon.com/tagged/blockchain) _for authentication now. It’s the_ [_future_](https://hackernoon.com/tagged/future)_!_

Cool. I’m just building a simple web app at the moment — a normal CRUD app using Rails, going to deploy to Heroku and use Auth0 for authentication with username and passwords to issue JWTs. Is that still the way to go?

_\-Oh no. That’s old school. Passwords are dead. Securely authenticating with a side channel is the way to go! It’s the future!_

Oh, Okay. What’s that?

_\-SQRL is a take on using a trusted device to authenticate you on websites. It bypasses the need to remember a weak human generated password. It’s the future!_

Squirrels? What? What do squirrels have to do with anything?

_\-Not squirrels, SQRL! It sounds like squirrel but it’s spelled SQRL._

SQRL. Okay, what is it?

_\-SQRL shows you a prompt which you click to authenticate. It’s basically a nonce that your computer signs, or a QR code that you scan so that your phone signs it. The signed nonce is sent back to the server and you’re in! It’s the future!_

So like Oauth and logging in with Facebook?

_\-No, Oauth is dead. Trusted third parties are dead! With SQRL you host the key on your own device! It’s the future!_

What? Wait, don’t users need to have a SQRL client installed on their devices to use it?

_\-Well, yeah, but they can get SQRL on their phones or install a computer client._

So people don’t have it on their devices?

_\-No, but they’ll catch on._

What? How? Who’s pushing the adoption for this? Google?

_\-Oh, no, Gibson wrote the draft for this._

Gibson? The guy in Brave Heart?

_\-Not Mel Gibson, Steve Gibson! The guy in the Security Now! podcast. He made SpinRite, the disk recovery tool and said that Microsoft engineered a RCE backdoor in Windows._

Microsoft engineered a backdoor in Windows?! What!

_\-Oh, no, he was wrong about that. But then he wrote the draft for SQRL._

Ummm, okay… so I need to add SQRL on my website?

_\-Oh, no! SQRL is dead. Use Blockstack’s Auth JS to authenticate with the blockchain! It’s the future!_

Wait, what? What’s Blockstack.

_\-It’s a distributed key-value store powered by a blockchain._

Like the bitcoin Blockchain?

_\-Yes, but no. Blockstack’s blockchain is for PKI, DNS and storing hashes._

So Blockstack has it’s own blockchain?

_\-No, it uses the bitcoin blockchain to store their virtual blockchain_

Like a side chain?

_\-Yes, but it’s a virtual blockchain._

Right, but what does this have to do with Authentication?

_\-Blockstack’s Authentication looks up the user’s key from the blockchain. So the server doesn’t need to store that either! It’s trustless. It’s the future!_

But the user still needs to manage the private key! What if i need to log in from my dad’s computer?

_\-Eventually someone will make a web based key store for private keys._

Like Lastpass?

_\-Yeah, but for private keys! It’ll be amazing!_

But then how will I log into that web based key store?

_\-Maybe with a unique user identifier and a secret string. It’ll be amazing!_

I see. So I need to authenticate my web application with Blockstack Auth, which users don’t have a stable client for, yet. It’s like SQRL, but not SQRL because it uses a virtual blockchain to store the keys, which is actually a side chain. Users will be tied to their devices until LastPass starts storing private keys, and then I can log into my site from my dad’s computer by logging into LastPass **with a username and password**?

_Yes! Isn’t it glorious?!_

I’m going with basic http-auth.

---

Thank you for reading this! If you have time and like alpha things, check out this app I’m building: [Mailpenny.com](https://mailpenny.com)

If you love distributed things, Blockstack is doing amazing work with their distributed DNS that may kill DNSSEC! Check them out at [blockstack.org](https://blockstack.org)

Big shoutout to Steve Gibson from _Security Now!_ for his podcast! It keeps me focused during my workout!

If you’re setting up authentication, I recommend [Auth0.com](https://auth0.com) to shave off weeks of development related to authentication. Their feature list is too long for me to list here.

This piece was inspired by my musings with [Kobi](http://kobigurk.com) and this [post](https://circleci.com/blog/its-the-future/) by CircleCI.

> [Hacker Noon](http://bit.ly/Hackernoon) is how hackers start their afternoons. We’re a part of the [@AMI](http://bit.ly/atAMIatAMI)family. We are now [accepting submissions](http://bit.ly/hackernoonsubmission) and happy to [discuss advertising &sponsorship](mailto:partners@amipublications.com) opportunities.

> To learn more, [read our about page](https://goo.gl/4ofytp), [like/message us on Facebook](http://bit.ly/HackernoonFB), or simply, [tweet/DM @HackerNoon.](https://goo.gl/k7XYbx)

> If you enjoyed this story, we recommend reading our [latest tech stories](http://bit.ly/hackernoonlatestt) and [trending tech stories](https://hackernoon.com/trending). Until next time, don’t take the realities of the world for granted!
