---
layout: post 
category : technology
title: Dual monitor and GTK theme on ubuntu
matheq: no
comments: yes
share: no
tags : [ubuntu 12.04, double screen, gtk, theme, ubuntu-tweak]
---



> Xrandr is used to set the size, orientation and/or reflection of the outputs for a screen.
> It can also set the screen size.

As stated above (by command `man xrandr`), xrandr could set screen resolution and position, and surely it is the ultimate weapon against dual screen on ubuntu while the `System -> Preferences -> Display` option down.
This following commands activate dual screen mode on ubuntu 12.04 (tested on my PC).
<script src="https://gist.github.com/dustincys/9149969.js"></script>
Anyway, things were not going smoothly, see, 

1. The file windows simultaneously show double menus
	![double menus, irritatingly display on the top of file window](https://2s66lw.blu.livefilestore.com/y2pGL5WMBWGPe5IuyTb5LSEOyo7WRsllNB89eL7EsQvq_HwMCLcuuC8EDqkeA5LeZmX_O_NL-kLcL1vlW1mcuSrHgrvd6Yx0MLHTeGgH0g04uo/bad.png "double menus, irritatingly display on the top of file window")
2. And it shows no response to GTK theme, which is not the worst
	![no response to gtk](https://2s66lw.blu.livefilestore.com/y2pdd4XMENQsneRBuPlLtHlcce1WBVju3mViuRdgdkkByk7mijKcvchR6EnsxI7VDgQIIIFkntHb-nSJMHxcbkdqewmDzVF4crgginDy-DPDsc/files.png "no response to gtk")
3. ubuntu pops this dialog box every time after login.
	![dialog box](https://2s66lw.blu.livefilestore.com/y2pKMbfkcQ8gSnT1AyU3B_m8DqqregKIY-NAB4kDfn1StaOOytarLWRCu1QPY45ZakKfuB3pHQ2HgCzDVQ8YMhoH0YXREhnKSGeOO1WRGbDNMc/unable.png "dialog box")

After gave several tries such as ubuntu-tweak or gnome-tweak-tool or myunity in vain, a tiny clue raises its hand finally.
While ubuntu uses gtk theme `elementary`, the button and background of selected text should be light blue rather than brown, but the dialog box retains the default color brown.

[Accordingly](http://askubuntu.com/questions/23869/could-not-apply-the-stored-configuration-for-the-monitor), remove the `monitors.xml` in the path `~/.config/` then there would be no login pop out dialog, and apparently it makes the gtk theme rendered smoothly.
![gtk theme](https://2s66lw.blu.livefilestore.com/y2pEilDet0SXuVOV5igDkGLM40pUoXkIJ3LaaBHnV9bXYAXmc_amK2_-d90s-iEXjgDKM2C16hrQqVPvFDUrVavJ0lLLiFG6dcYkgPNUruXfs0/good.png "gtk theme")
