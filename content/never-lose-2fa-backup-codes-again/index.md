---
title: "Never Lose 2FA Backup Codes Again"
description: "Sometimes don’t print my Two-Factor Authentication backup codes all the time. I’m either not near a printer, or I’m just being lazy…"
date: "2014-09-04T00:00:00.000Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/never-lose-2fa-backup-codes-again-6c767d9edbec
redirect_from:
  - /never-lose-2fa-backup-codes-again-6c767d9edbec
---

Never Lose 2FA Backup Codes Again

Sometimes don’t print my Two-Factor Authentication backup codes all the time. I’m either not near a printer, or I’m just being lazy. Although, finally, after being locked out of my account a bunch of times, I worked out a way to never let that happen again. Here’s what you need:

-   A Gmail account
-   A PGP Key — extra laziness points if it’s published on a keyserver

Got those? Perfect. Do this:

Now if you never need your codes, just search for `to:youremail+2fa$service@gmail.com` in your gmail and voila. The lazy man’s secure backup. **Remember, this is a backup of your codes,** not the primary method to be storing your codes. This is no replacement for a good old fashioned printout! What do you think you’ll do if you lose access to your Gmail?

This works because Gmail ignores anything after the `+` sign after your username. You can send an email to `youremail+whatever@gmail.com` and the email will always show up in your inbox.

_Freebie: When signing up for dodgy websites, use your_`[_email+dodgywebsite@gmail.com_](https://amin.gilani.me/cdn-cgi/l/email-protection)` _as your email address. That way if they leak your email address to spammers, you can simply set a filter to direct all mail to that email address into your Spam._

**Never Lose 2FA Backup Codes Again** was published on September 04, 2014.

---

_Originally published at_ [_//amin.gilani.me/geeking-out/2014/09/04/never-lose-2fa-backup-codes-again/_](//amin.gilani.me/geeking-out/2014/09/04/never-lose-2fa-backup-codes-again/) _on September 4, 2014._
