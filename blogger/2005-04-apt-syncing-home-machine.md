<!--
date: '2005-04-19'
published: true
slug: 2005-04-apt-syncing-home-machine
time_to_read: 5
title: APT syncing a home machine
-->

Thanks to [Hellkom](www.hellcom.co.za), its not worth it for me (or any South African for that matter) to get an ADSL line at home. I won't even mention dialup (ok I have, but I regret it). So this creates difficulties. One of them is the fact that it is a pain to keep my home maching up to date with the latest ubuntu packages.  
  
I sought advice and I found it (courtesy Thomas Fogwill):  
  
There are at least 3 other ways to do what you want:  
1) Repository on notebook  
2) Manually generate fetch lists  
3) Use automated tools  
  
(1) Repository on notebook (I do this)  
I keep my downloaded packages on my notebook  
(in /var/cache/apt/archives/). Things I want to install at home, but not  
on my notebook, are downloaded with apt-get -d install ...  
I have a www directory linked to /var/cache/apt/archives/,  
and generate a Packages.gz file here like this:  
apt-ftparchive packages . | gzip -c > Packages.gz  
  
Then, I add this www directory to my wife's sources.list (at home). If  
any packages are ever missing from this dir, I rebuild them with  
dpkg-repack.  
  
The following is a useful little script to rebuild ALL installed  
packages:  
dpkg --get-selections | grep [^De]install | cut -f1 | sh -c "while read STRIN; do dpkg-repack \$STRIN ;done"  
  
Note: dpkg-repack uses the files on the filesystem to rebuild the  
package. Thus, any config/customisation you've done will be included in  
the deb.  
  
2) Manually generate fetch lists  
This should also work (untested). Apt stores its downloaded package  
files here: /var/lib/apt/lists/  
You should be able to copy your updated files over from your notebook,  
then do an apt-get --print-uris install|upgrade|dist-upgrade on the home  
machine. This will print out the uri's of the files that need to be  
downloaded. You then take these uri's, download them (at work) with  
wget, copy them to the home machine and dpkg -i \*.deb to install them.  
  
This will dump the apt-get output into a file that wget can use to  
download in batch mode:  
apt-get --print-uris -y install ... | grep http | cut -f1 -d' ' | cut -f2 -d\' > debs.toget  
To batch fetch the debs:  
wget -i debs.toget   
  
This should work fairly well, except when packages on the mirror change overnight.   
  
3) Use automated tools  
e.g. apt-zip. apt-zip basically automates (2) above.

[Original post](https://ysfk.blogspot.com/2005/04/apt-syncing-home-machine.html)

#linux #legacy-blogger 