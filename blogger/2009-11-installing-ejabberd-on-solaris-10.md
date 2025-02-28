<!--
date: '2009-11-09'
published: true
slug: 2009-11-installing-ejabberd-on-solaris-10
time_to_read: 5
title: Installing eJabberd on Solaris 10
-->

1stly, a disclaimer: This is not meant to be a tutorial, even though I've catrgorised this as a "HowTo". It's merely a record of how I managed to get eJabberd running on my Solaris 10 machines (Note - important for later: saying this before I've actually got it working)  
  
What I have:  

  
* 1. Sun T5120
  
* 2. Solaris 10
  
* 3. Erlang R12B-5
  

  
Other Ingredients:  

  
* 1. eJabberd source
  
* 2. Missing Gnu Packages
  

  
Method:  
  
These are some of the other packages I needed to get:  

  
1. [Gnu Install](ftp://sunfreeware.saix.net/pub/solaris-freeware/sparc/10/coreutils-6.4-sol10-sparc-local.gz)
  
2. [Gnu Make](ftp://sunfreeware.saix.net/pub/solaris-freeware/sparc/10/make-3.81-sol10-sparc-local.gz)
  
3. [libiconv](ftp://sunfreeware.saix.net/pub/solaris-freeware/sparc/10/libiconv-1.11-sol10-sparc-local.gz)
  
4. [Expat](ftp://ftp.sunfreeware.com/pub/freeware/sparc/10/expat-2.0.1-sol10-sparc-local.gz)
  
5. [OpenSSL](ftp://sunfreeware.saix.net/pub/solaris-freeware/sparc/10/openssl-0.9.8h-sol10-sparc-local.gz)
  

  
Installed them by 1st unpacking:  
gunzip coreutils-6.4-sol10-sparc-local.gz  
and then:  
pkgadd -d coreutils-6.4-sol10-sparc-local  
(as su)  
  
Next download [ejabberd-2.1.0\_rc2.tar.gz](http://www.process-one.net/downloads/ejabberd/2.1.0-rc2/ejabberd-2.1.0_rc2.tar.gz)  
  
Unpack into a source folder:  
gunzip ejabberd-2.1.0\_rc2.tar.gz  
tar -xvf ejabberd-2.1.0\_rc2.tar  
  
Then, in the ejabberd-2.1.0\_rc2 folder, go to src directory, after having a quick peak at README  
  
This is the vital bit, set your path to include the following:  
export PATH=$PATH/usr/local/bin:/usr/sfw/bin:/usr/ucb:/usr/bin:/usr/sbin:/usr/ccs/bin:/usr/ucb:/etc:/usr/local/erlang/R12B-5/bin:  
  
At this point, I tried:  
./confgure  
which worked, followed by a:  
make install  
which failed horribly.  
  
To fix this, I had to edit the main and nested Makefiles:  
ERLANG\_CFLAGS= -I/usr/local/erlang/R12B-5/lib/erlang/lib/erl\_interface-3.5.9/include **-I/usr/local/erlang/R12B-5/lib/erlang/usr/include**  
  
Also had to change ejabberd\_s2s\_in.erl as follows:  
  
-include\_lib("**ssl/pkix/**PKIX1Explicit88.hrl").  
-include\_lib("**ssl/pkix/**PKIX1Implicit88.hrl").  
  
Thereafter make install worked.  
  
Next edit /sbin/ejabberdctl and change the 1st line to:  
#!/usr/bin/bash  
so that it uses the correct shell.  
  
And voila!  
  
Update:  
  
Discovered a problem, which prevented my server from establishing server to server connections, kept getting "ejabberd.im ejabberd remote server not found" .  
  
[This](http://www.ejabberd.im/node/3714) article helped solve the bug, which involved commenting out line 275 of ejabberd\_s2s\_out.erl, before doing a make. All is fine again now.

[Original post](https://ysfk.blogspot.com/2009/11/installing-ejabberd-on-solaris-10.html)

#howto #legacy-blogger 