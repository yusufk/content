<!--
date: '2011-04-13'
published: true
slug: 2011-04-preparing-multimedia-for-sony-dav-tz130
time_to_read: 5
title: Preparing Multimedia for Sony DAV TZ130 DVD player USB
-->

Bear with me while I attempt preparing a mencoder command that converts my multimedia files into something that this darn DVD player can understand.  
> mencoder -mc 0 -noskip -vf expand=:::::16/9,scale=720:480,hqdn3d,harddup -ovc xvid -oac lavc -channels 6 -xvidencopts fixed\_quant=3.8:me\_quality=6:noqpel:nogmc:trellis:chroma\_me:  
> chroma\_opt:hq\_ac:vhq=4:lumi\_mask:max\_key\_interval=300:quant\_type=mpeg:  
> max\_bframes=2:closed\_gop:nopacked:profile=asp5:autoaspect:bvhq=1   
> -lavcopts acodec=ac3 -o outfile.avi

  
The player thinks about playing the file..... then stops thinking and returns to the menu. :(  
  
This works, but only 2 Audio channels:  
> mencoder -mc 0 -noskip -vf expand=:::::16/9,scale=720:576,hqdn3d,harddup -ovc xvid -oac mp3lame -xvidencopts fixed\_quant=3.8:me\_quality=6:noqpel:nogmc:trellis:chroma\_me:  
> chroma\_opt:hq\_ac:vhq=4:lumi\_mask:max\_key\_interval=300:quant\_type=mpeg:  
> max\_bframes=2:closed\_gop:nopacked:profile=asp5:autoaspect:bvhq=1   
> -lameopts vbr=2:q=6:aq=2 -o output.avi input.m4v

[Original post](https://ysfk.blogspot.com/2011/04/preparing-multimedia-for-sony-dav-tz130.html)

#howto #technology #multimedia #legacy-blogger 