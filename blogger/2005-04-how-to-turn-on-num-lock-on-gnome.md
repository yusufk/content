<!--
date: '2005-04-29'
published: true
slug: 2005-04-how-to-turn-on-num-lock-on-gnome
time_to_read: 5
title: How to turn on Num Lock on GNOME startup?
-->

[Unofficial Ubuntu 5.04 Starter Guide](http://www.ubuntuguide.org/#numlockx): "
  
  
sudo apt-get install numlockx
  
sudo cp /etc/X11/gdm/Init/Default /etc/X11/gdm/Init/Default\_backup
  
sudo gedit /etc/X11/gdm/Init/Default
  
  
 4. Find this line
  
  
...
  
exit 0
  
  
 5. Add the following lines above it
  
  
if [ -x /usr/bin/numlockx ]; then
  
 /usr/bin/numlockx on
  
fi
  
  
 6. Save the edited file (sample)
  
 7. Read How to restart GNOME without rebooting computer?"

[Original post](https://ysfk.blogspot.com/2005/04/how-to-turn-on-num-lock-on-gnome.html)

#linux #legacy-blogger 