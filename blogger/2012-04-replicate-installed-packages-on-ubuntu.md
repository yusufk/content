<!--
date: '2012-04-04'
published: true
slug: 2012-04-replicate-installed-packages-on-ubuntu
time_to_read: 5
title: 'Replicate installed packages on an Ubuntu machine to another:'
-->

  
  
Backup installed package list on current machine  
dpkg --get-selections > selections.txt  
  
move selections.txt to the new machine Set package list on new machine and install packages  
dpkg --set-selections < selections.txt  
apt-get update  
apt-get upgrade

**Google+:** [View post on Google+](https://plus.google.com/103392016560023386646/posts/gaw8NjLND5W)

  
  
*Post imported by Google+Blog. Created By [Daniel Treadwell](http://minimali.se/).*

[Original post](https://ysfk.blogspot.com/2012/04/replicate-installed-packages-on-ubuntu.html)

#google+ #legacy-blogger 