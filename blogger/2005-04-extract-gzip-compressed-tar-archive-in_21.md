<!--
date: '2005-04-21'
published: true
slug: 2005-04-extract-gzip-compressed-tar-archive-in_21
time_to_read: 5
title: Extract a gzip compressed tar archive in Linux
-->

To extract the archive filename.tar.gz into the current directory:  
  
  
tar xzf filename.tar.gz   
  
  
If this fails, the version of tar may not support gzip compression. In this case, you can use the traditional two-stage command:  
  
  
gzip -dc filename.tar.gz | tar xf -

[Original post](https://ysfk.blogspot.com/2005/04/extract-gzip-compressed-tar-archive-in_21.html)

#linux #legacy-blogger 