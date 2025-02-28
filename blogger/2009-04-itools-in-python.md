<!--
date: '2009-04-17'
published: true
slug: 2009-04-itools-in-python
time_to_read: 5
title: iTools in Python
-->

Calculating Islamic prayer times can be simple, if you are outside and have stick (where you can check if its sunrise, sunset, mid-day etc.) or quite complex if you want to calculate whether it's sunrise, sunset, mid-day etc. Thankfully, there are people who have done the complex calculations and others that have pulled these into software.  
  
Unfortunately however, the geniuses at <http://www.arabeyes.org/> decided to use c as their preferred language for the iTools project. iTools is available as a package on Ubuntu, as well as libitl, the library where all the smart stuff happens. The guys at arabeyes were kind enough to also include with the libitl source code an example perl wrapper and the SWIG configuration files thereof!  
  
A few hours of tinkering with SWIG got me to the point where I can succesfully calculate Salaah times using a decent programming language (Python).  
  
[Here](http://yusufk.googlepages.com/pyITL.tar.gz) is the wrapper library, compiled object and example code for anyone that wants it. I will explain the process in making the attached when I have more time (InshaAllah).  
  
For anyone wishing to roll their own, download the [SWIG interface file](http://yusufk.googlepages.com/libitl_py.i) and [Makefile](http://yusufk.googlepages.com/Makefile) and place these in the swig folder of the libitl source package. Build the itl source before running "make python" in the swig directory.



## 2 comments captured from [original post](https://ysfk.blogspot.com/2009/04/itools-in-python.html) on Blogger

**Jameel Haffejee said on 2009-07-01**

Hmmm im pretty sure you could have written it in pure python , i know i did converted another project into C#

**Yusuf said on 2009-07-01**

Pretty sure I can, but the getting hold of the mathematics and rules is the tricky part.



[Original post](https://ysfk.blogspot.com/2009/04/itools-in-python.html)

#legacy-blogger 