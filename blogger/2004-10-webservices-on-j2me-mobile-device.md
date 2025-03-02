<!--
date: '2004-10-14'
published: true
slug: 2004-10-webservices-on-j2me-mobile-device
time_to_read: 5
title: Webservices on a J2ME mobile device
-->

My latest experimenting with J2ME has led me to webservices. I've  
managed to communicate with several online webservice providers  
including http://www.xmethods.net/ and http://www.google.com/apis/ . I  
managed to do this using the small footprint SOAP package kSOAP  
http://ksoap.enhydra.org/ or http://www.ksoap.org/ .Here is a copy of  
the template java midlet that I use to communicate to web-services  
with:  
  
Template.java  
```
import java.io.IOException;  
  
import javax.microedition.lcdui.Command;  
import javax.microedition.lcdui.CommandListener;  
import javax.microedition.lcdui.Display;  
import javax.microedition.lcdui.Displayable;  
import javax.microedition.lcdui.Form;  
import javax.microedition.lcdui.ImageItem;  
import javax.microedition.lcdui.StringItem;  
import javax.microedition.lcdui.TextBox;  
import javax.microedition.lcdui.TextField;  
import javax.microedition.midlet.MIDlet;  
import javax.microedition.midlet.MIDletStateChangeException;  
  
import org.ksoap.SoapObject;  
import org.ksoap.transport.HttpTransport;  
  
/\*\*  
 \* @author Yusuf  
 \*   
 \*/  
public class Template extends MIDlet implements CommandListener {  
 private Display display;  
  
 private String url = "";  
  
 private String nameSpace = "";  
  
 private String name = "";  
  
 private String key = "";  
  
 private Command sendCommand;  
  
 private Command exitCommand;  
  
 private Command backCommand;  
  
 private StringItem stringItem;  
  
 private Form form1;  
  
 private TextField textField1, textField2;  
  
 private String choice;  
  
 private ImageItem background;  
  
 public Template() {  
 display = Display.getDisplay(this);  
 stringItem = new StringItem("", "");  
 textField1 = new TextField("Input 1:", choice, 30,  
TextField.ANY);  
 textField2 = new TextField("Input 2:", choice, 30,  
TextField.ANY);  
 exitCommand = new Command("Exit", Command.EXIT, 1);  
 sendCommand = new Command("Invoke", Command.SCREEN, 1);  
 backCommand = new Command("Back", Command.BACK, 1);  
 background = new ImageItem("", null,  
ImageItem.LAYOUT\_CENTER, "no pic");  
  
 // TODO Auto-generated constructor stub  
 }  
  
 /\*  
 \* (non-Javadoc)  
 \*   
 \* @see javax.microedition.midlet.MIDlet#startApp()  
 \*/  
 protected void startApp() throws MIDletStateChangeException {  
 form1 = new Form("Webservices");  
 try {  
 //background.setImage(Image.createImage("/google.png"));  
 url = getAppProperty("URL");  
 nameSpace = getAppProperty("NAMESPACE");  
 name = getAppProperty("NAME");  
 key = getAppProperty("KEY");  
 //form1.append(background);  
 form1.append(textField1);  
 form1.append(textField2);  
 form1.append(stringItem);  
 form1.addCommand(sendCommand);  
 form1.addCommand(exitCommand);  
 form1.setCommandListener((CommandListener)  
this);  
 display.setCurrent(form1);  
  
 // TODO Auto-generated method stub  
  
 } catch (Exception e) {  
 // TODO Auto-generated catch block  
 System.out.println(e);  
 e.printStackTrace();  
 }  
  
 }  
  
 /\*  
 \* (non-Javadoc)  
 \*   
 \* @see javax.microedition.midlet.MIDlet#pauseApp()  
 \*/  
 protected void pauseApp() {  
 // TODO Auto-generated method stub  
  
 }  
  
 /\*  
 \* (non-Javadoc)  
 \*   
 \* @see javax.microedition.midlet.MIDlet#destroyApp(boolean)  
 \*/  
 protected void destroyApp(boolean arg0) throws  
MIDletStateChangeException {  
 // TODO Auto-generated method stub  
  
 }  
  
 public void doInvoke(String in1, String in2) throws Exception {  
 StringBuffer stringBuffer = new StringBuffer();  
 TextBox textBox = null;  
 SoapObject client = new SoapObject(nameSpace, name);  
 //client.addProperty("LKEY", "0");  
 //client.addProperty("FromName", "Yusuf");  
 //client.addProperty("ToUserID",  
"yusufk18@hotmail.com");  
 //client.addProperty("Message", "Watse");  
 //client.addProperty("CityName", "Pretoria");  
 //client.addProperty("CountryName", "South Africa");  
 //client.addProperty("myString", "hello");  
 client.addProperty("FromCurrency", in1);  
 client.addProperty("ToCurrency", in2);  
 HttpTransport ht = new HttpTransport(url, nameSpace);  
 try {  
 stringBuffer.append(ht.call(client));  
  
 } catch (IOException e) {  
 // TODO Auto-generated catch block  
 System.out.println(e);  
 e.printStackTrace();  
 System.out.println(client.getNamespace());  
  
 }  
 stringItem.setText(stringBuffer.toString());  
 System.out.println(stringBuffer);  
 }  
  
 /\*  
 \* (non-Javadoc)  
 \*   
 \* @see  
javax.microedition.lcdui.CommandListener#commandAction(javax.microedition.lcdui.Command,  
 \* javax.microedition.lcdui.Displayable)  
 \*/  
 public void commandAction(Command command, Displayable arg1) {  
 if (command == sendCommand) {  
  
 Thread t = new Thread() {  
 String input1 = textField1.getString();  
  
 String input2 = textField2.getString();  
  
 public void run() {  
 try {  
 doInvoke(input1,  
input2);  
 } catch (Exception e) {  
 e.printStackTrace();  
 }  
 }  
 };  
 t.start();  
  
 } else if (command == backCommand) {  
  
 display.setCurrent(form1);  
  
 }  
  
 else if (command == exitCommand) {  
 try {  
 destroyApp(false);  
 notifyDestroyed();  
 } catch (Exception e) {  
 e.printStackTrace();  
 }  
  
 }  
  
 }  
  
}  
```


[Original post](https://ysfk.blogspot.com/2004/10/webservices-on-j2me-mobile-device.html)

#programming #mobile #legacy-blogger 