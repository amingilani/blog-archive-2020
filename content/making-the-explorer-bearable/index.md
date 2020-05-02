---
title: "Making the Explorer Bearable"
description: "Considering how generous Jaggyjags was to make and release a custom ROM for us, I thought I might pay him back (and help the new people) by…"
date: "2012-07-23T00:00:00.000Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/making-the-explorer-bearable-5acee52e4ef7
redirect_from:
  - /making-the-explorer-bearable-5acee52e4ef7
---

Making the Explorer Bearable

Considering how generous [Jaggyjags](http://forum.xda-developers.com/member.php?u=4375224) was to make and release a custom ROM for us, I thought I might pay him back (and help the new people) by writing a good, easy to follow tutorial on rooting the HTC Explorer (Pico) and installing JaggyRom. This tutorial will be broken into five parts: Unlocking the Bootloader, Installing a custom Recovery, Rooting, Partitioning the SD Card, and Flashing JaggyRom. The instructions here will walk you through everything so if you’re just rooting, follow to where you’re rooted. Before you do anything, install HTC Sync from [here](http://www.htc.com/www/help/htc-explorer/#download).

This tutorial simplifies Jaggyjag’s rooting guide [here](http://forum.xda-developers.com/showpost.php?p=20763212&postcount=1), and mahmadaq’s guide [here](http://forum.xda-developers.com/showpost.php?p=24242126&postcount=948).

Note: This information is provided as is, I will not be held responsible for any damage you do to your phone.

### Unlocking The Bootloader

Warning: unlocking your Bootloader will probably void your warranty!

This will be short, go [here](http://www.htcdev.com/bootloader) and follow along. Choose “all other supported models” because the Explorer isn’t listed.

Done? Yay! Lol, don’t worry, the rest gets easier

### Installing a custom Recovery

Now, the default Recovery on the phone isn’t all that powerful, what we want is to be able to flash a ROM straight from the SD card. Jaggyjags was kind enough to simplify the entire process.

1.  First download [this](http://forum.xda-developers.com/attachment.php?attachmentid=913094&d=1329843100) to your computer.
2.  Now switch your phone off, take out the battery, plug it back
3.  Press and hold the volume down button, and the power button.
4.  Verify that you’re at the Bootloader. See the three funny skateboarding Androids? Good.
5.  Connect your phone to the computer with a USB cable.
6.  Click Fastbook, it’s the first option.
7.  Now extract the downloaded file, and click _Recovery.bat_
8.  Make a backup of your current install (instructions at the bottom) — strongly recommended!
9.  Done!

_Do not use the Clockwork Recovery Mod. It doesn’t have proper ext support. No, really, JaggyRom won’t be able to move stuff to the ext partition. Fine, if you really must.. go on, try it, but don’t say I didn’t warn you._

### Rooting

You’re almost there, now for the really easy bit

1.  Download [this](http://forum.xda-developers.com/attachment.php?attachmentid=832400&d=1325076959).
2.  Copy it on your SD card
3.  Boot to Recovery (instructions at the bottom)
4.  Install the zip file (instructions at the bottom)
5.  Done!

### Partitioning the SD Card

What you need is an ext3 or ext4 partition on your SD card for Jaggyjags to transfer stuff there, most people use pc based tools to partition the SD card, I find it easier and simpler just to do it through Recovery.

Warning: backup your data, this will destroy it! Instructions at the bottom.

1.  Boot to Recovery (instructions at the bottom)
2.  Advanced>Partition SD card
3.  Select an Ext size — max 2048
4.  Set the swap to zero
5.  Done!

Regardless of how you partition it, you’re safe as long as your keep the partition size less than 2 GB. Also, if you’re using JaggyRom, you don’t need a swap, set it to zero, i can’t vouch for other ROMs though.

### Installing JaggyRom

This bit will be divided into three sections: Wiping Data; which should always be done before installing a new ROM, Installing JaggyRom and Upgrading JaggyRom; which teaches you how to upgrade JaggyRom (if a new version is out) without losing your data.

Before you do anything, download the latest version of JaggyRom [here](http://forum.xda-developers.com/showthread.php?t=1473218), and place it on the root of your SD Card, by root, I mean don’t put it in any folders, put it right at the beginning. Do this now!

Warning: backup your data, this will destroy it! Instructions at the bottom.

Wiping Data:

1.  Boot to Recovery (instructions at the bottom)
2.  Select _wipe data/factory reset,_ and confirm
3.  Select _advanced_\>_Wipe Dalvik Cache_, and confirm
4.  Almost done!

Installing JaggyRom:

1.  Boot to Recovery (instructions at the bottom)
2.  Install the zip file for JaggyRom (instructions at the bottom)
3.  Wait until it says the install is complete.
4.  Reboot the device
5.  Wait for it, wait for it, and just when you think it’s all gone to hell, wait some more…
6.  After about ten to fifteen minutes, it should show your homescreen.
7.  Wait one more minute before unlocking and it’s ready.
8.  All done!

Upgrading JaggyRom**:**

1.  First do a [Titanium Backup](https://play.google.com/store/apps/details?id=com.keramidas.TitaniumBackup&hl=en) of your apps
2.  Boot to Recovery (instructions at the bottom)
3.  Select _advanced_\>_Wipe Dalvik Cache_, and confirm
4.  Now install the zip file (instructions at the bottom)
5.  Cross your fingers, and let it boot up..
6.  If it gets stuck at the HTC logo, just run Fix Permissions from Recovery..
7.  All done!
8.  If it didn’t work, do a fresh install of JaggyRom, and restore from your Titanium Backup

### Misc.

Booting to Recovery:

1.  Switch your phone off
2.  Take the battery out
3.  Plug it back in
4.  Press and hold the Volume Down and Power buttons
5.  Wait until you’re at the Bootloader with three skating Androids
6.  Navigate to Recovery using the Volume buttons and select using the Power button.

Installing a zip_:_

1.  Boot to Recovery
2.  Select _Install zip from sdcard_
3.  Select _choose zip from sdcard_
4.  Navigate to your zip file
5.  Confirm with a Yes
6.  Let it Install
7.  Done!

Making a backup:

1.  Boot to Recovery
2.  Select _backup and restore_
3.  Select _backup_
4.  Done!

Congratulations, you’ve gotten rid of those pesky low internal memory signs! Personally, a day before publishing this, I moved away from JaggyRom because while it was great, it just wasn’t stable enough on my phone.. probably because I didn’t have the right kind of SD Card. However, because I realized stability is of the utmost importance to my phone habits, I went back to the stock ROM, and installed Link2SD… I’m actually very happy with my decision and might do a tutorial on that later.. but i’m just so lazy. Let me know if you find any mistakes.. And I won’t answer stupid questions.

**Update:** a few really developers at XDA got together and ported Cyanogen Mod 9 to the Pico! Cyanogen Mod 9 is a ROM based on Ice Cream Sandwich, only it’s packed with more features! I must say, it’s the best ROM i’ve tried so far, even better than the stock ROM! Link to thread is [here](http://forum.xda-developers.com/showthread.php?t=1821582).

**Making the Explorer Bearable** was published on July 23, 2012.

---

_Originally published at_ [_//amin.gilani.me/geeking-out/2012/07/23/making-the-explorer-bearable/_](//amin.gilani.me/geeking-out/2012/07/23/making-the-explorer-bearable/) _on July 23, 2012._
