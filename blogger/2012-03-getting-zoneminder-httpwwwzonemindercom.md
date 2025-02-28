<!--
date: '2012-03-21'
published: true
slug: 2012-03-getting-zoneminder-httpwwwzonemindercom
time_to_read: 5
title: 'Getting ZoneMinder ( http://www.zoneminder.com/ ) to work with Philips

  900NC webcam...'
-->

Getting ZoneMinder ( <http://www.zoneminder.com/> ) to work with Philips 900NC webcam on Ubuntu requires some tweaking:  
  
echo 134217728 >/proc/sys/kernel/shmall && echo 134217728 >/proc/sys/kernel/shmmax  
  
Add:  
  
kernel.shmall = 167772160  
kernel.shmmax = 167772160  
to /etc/sysctl.conf   
sudo chmod 666 /dev/video0  
  
Maximum FPS 15  
NTSC M  
YUV420  
640x480

**Embedded Link**

  

![](http://images0-focus-opensocial.googleusercontent.com/gadgets/proxy?container=focus&gadget=a&resize_h=100&url=http%3A%2F%2Fwww.zoneminder.com%2Fsites%2Fzoneminder.com%2Ffiles%2Fstyles%2Fmedium%2Fpublic%2FScreenshot-Home%2520-%2520Montage%2520-%2520Mozilla%2520Firefox.jpg)

  
 [ZoneMinder - ZoneMinder: Linux Home CCTV and Video Camera Security with Motion Detection](http://www.zoneminder.com/)  
 ZoneMinder is a free video camera security application suite, designed for low cost DIY video security including commercial or home CCTV, theft prevention and child or family member monitoring includi...

**Google+:** [View post on Google+](https://plus.google.com/103392016560023386646/posts/CVP8cnweMVZ)

  
  
*Post imported by Google+Blog. Created By [Daniel Treadwell](http://minimali.se/).*

[Original post](https://ysfk.blogspot.com/2012/03/getting-zoneminder-httpwwwzonemindercom.html)

#google+ #legacy-blogger 