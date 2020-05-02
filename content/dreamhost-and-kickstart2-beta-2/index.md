---
title: "DreamHost and Kickstart2 Beta 2"
description: "I was checking out Kickstart version 7.x-2.0-beta2 on my Dreamhost.com shared account when i ran into a few problems, here’s a quick…"
date: "2012-08-27T00:00:00.000Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/dreamhost-and-kickstart2-beta-2-f2519d87d84d
redirect_from:
  - /dreamhost-and-kickstart2-beta-2-f2519d87d84d
---

DreamHost and Kickstart2 Beta 2

I was checking out Kickstart version 7.x-2.0-beta2 on my Dreamhost.com shared account when i ran into a few problems, here’s a quick two-step fix.

### The Error

When installing core, and setting up modules for the sample store, I got this error:

```
An AJAX HTTP error occurred. HTTP Result Code: 200 Debugging information follows. Path http://commercekickstart/install.php?profile=commerce_kickstart&amp;locale=en&amp;id=2&amp;op=do StatusText: OK ResponseText: Home | Commerce Kickstart @import url("http://commercekickstart/modules/system/system.base.css?m5npxc"); @import url("http://commercekickstart/modules/system/system.theme.css?m5npxc"); @import url("http://commercekickstart/modules/system/system.menus.css?m5npxc"); @import url("http://commercekickstart/modules/system/system.messages.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/modules/contrib/tipsy/stylesheets/tipsy.css?m5npxc"); @import url("http://commercekickstart/misc/ui/jquery.ui.core.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/themes/commerce_kickstart_admin/jquery.ui.theme.css?m5npxc"); @import url("http://commercekickstart/modules/overlay/overlay-parent.css?m5npxc"); @import url("http://commercekickstart/misc/ui/jquery.ui.slider.css?m5npxc"); @import url("http://commercekickstart/modules/comment/comment.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/modules/commerce_kickstart/commerce_kickstart_menus/commerce_kickstart_menus.css?m5npxc"); @import url("http://commercekickstart/modules/field/theme/field.css?m5npxc"); @import url("http://commercekickstart/modules/node/node.css?m5npxc"); @import url("http://commercekickstart/modules/user/user.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/modules/contrib/views/css/views.css?m5npxc"); @import url("http://commercekickstart/modules/system/system.admin.css?m5npxc"); @import url("http://commercekickstart/modules/system/system.maintenance.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/modules/contrib/ctools/css/ctools.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/modules/contrib/views_slideshow/views_slideshow.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/themes/commerce_kickstart_admin/reset.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/themes/commerce_kickstart_admin/style.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/themes/commerce_kickstart_admin/contrib.css?m5npxc"); @import url("http://commercekickstart/profiles/commerce_kickstart/themes/commerce_kickstart_admin/commerce_kickstart_admin.css?m5npxc"); Home Installation tasksChoose language(done)Verify requirements(done)Set up database(done)Install profile(done)Configure site(done)Configure store(done)Import products(active)Finished SQLSTATE[23000]: Integrity constraint violation: 1048 Column 'fid' cannot be null Proudly built by Commerce Guys
```

The problems turned out to be broken support for PHP 5.2 and then (atleast for me) a low setting for _memory\_limit_.

### Switch to PHP 5.3

1.  Go to the [domain manager](https://panel.dreamhost.com/index.cgi?tree=domain.manage&) and edit the settings for your domain.
2.  Under _PHP mode_, select _PHP 5.3.x FastCGI_
3.  Save and wait a few minutes for the settings to take effect

### Bump up memory\_limit

At the time I’m writing this, the default setting for _memory\_limit_ is _90M_, which isn’t enough for Kickstart2, so do this:

```
$ cd ~
$ mkdir -p ~/.php/5.3 $ cd ~/.php/5.3
$ cp /etc/php53/php.ini phprc #Copies the current php.ini to the override
$ sed -i 's/memory_limit = "90M"/memory_limit = "150M"/g' phprc # Bump up to 150M
$ killall php53.cgi #Force the new settings to take effect[/sourcecode]
```

**DreamHost and Kickstart2 Beta 2** was published on August 27, 2012.

---

_Originally published at_ [_//amin.gilani.me/geeking-out/2012/08/27/dreamhost-and-kickstart2-beta-2/_](//amin.gilani.me/geeking-out/2012/08/27/dreamhost-and-kickstart2-beta-2/) _on August 27, 2012._
