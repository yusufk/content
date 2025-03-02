<!--
date: '2005-04-21'
published: true
slug: 2005-04-how-to-make-ubuntudebian-deb-packages
time_to_read: 5
title: How to make Ubuntu/Debian .deb packages from source  tar.gz
-->

This is my abbrevitated version of : [Hands On](http://www.geniusweb.com/LDP/HOWTO/Debian-Binary-Package-Building-HOWTO/x83.html)
  
Step 1: Make the source files
  
Un-tar your source files. This should result in a directory ./the\_app
  
cd into the\_app directory: cd the\_app
  
Make the application according to the instructions in the README file, usually just means running the make command in the the\_app directory: ./make
  
  
Step 2: Prepare the "control" file
  
Then create a directory DEBIAN: mkdir DEBIAN
  
cd into DEBIAN: cd DEBIAN
  
Create a file called "control" based on the following example:
  
  
Package: your\_package\_name\_without\_ext
  
Version: 1.0
  
Section: base
  
Priority: optional
  
Architecture: all
  
Depends: prog1 (>= 2.05a-11), prog2 (>= 2.0-12), prog3, prog4 (>= \ 1:2.0.7-8), prog5 (>= 3.02-8), prog6 (>= 2.4.2-3), prog7 (>= 5.0-5)
  
Maintainer: Yusuf
  
Description: A little sumthing sumthing on your program
  
  
Step 3: Put all the files in their places
  
Now you've got to create a directory structure with the files needed as they will be installed on your system.
  
So if you need the bin files in your /usr/local/bin directory then copy the bin files into the\_app/usr/local/bin : cp the\_app.sh usr/local/bin
  
  
Step 4: Create the Package
  
Decend into the directory containing the\_app and run: dpkg-deb --build the\_app
  
Thats it! You should now have a the\_app.deb package
  
  

[Original post](https://ysfk.blogspot.com/2005/04/how-to-make-ubuntudebian-deb-packages.html)

#linux #legacy-blogger 