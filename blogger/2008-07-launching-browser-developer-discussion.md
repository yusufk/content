<!--
date: '2008-07-08'
published: true
slug: 2008-07-launching-browser-developer-discussion
time_to_read: 5
title: launching browser - Developer Discussion Boards
-->

[launching browser - Developer Discussion Boards](http://discussion.forum.nokia.com/forum/showthread.php?t=60292&highlight=platformrequest): "public class Launcher extends MIDlet {  
Alert alert;  
public void startApp() {  
boolean b;  
try {  
b=platformRequest('http://www.mytoday.com/');  
destroyApp(true);  
notifyDestroyed();  
}  
catch (ConnectionNotFoundException ex)  
{  
ex.printStackTrace();  
}  
  
destroyApp(true);  
notifyDestroyed();  
  
}  
  
public void pauseApp() {  
}  
  
public void destroyApp(boolean unconditional) {  
}  
}"

[Original post](https://ysfk.blogspot.com/2008/07/launching-browser-developer-discussion.html)

#legacy-blogger 