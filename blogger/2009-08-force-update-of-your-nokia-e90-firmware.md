<!--
date: '2009-08-28'
published: true
slug: 2009-08-force-update-of-your-nokia-e90-firmware
time_to_read: 5
title: Force an update of your Nokia E90 Firmware
-->

While browsing the Nokia site under the Software and Support section for the E90 I noticed:

  

“![](http://europe.nokia.com/NOKIA_COM_1/Web_Applications/nokiaa/Common/image/1x1trans.gif)Nokia E90 Communicator software version 07.40.1.2 released.”

  

So I downloaded the software updater and checked for an update. I was disappointed to see that although my phone was on version 300.34.84, there was no update available. So I decided to scratch around a little more and I found that the issue was that the problem was that the product code for my E90 was “0550676”. This is the South African, Mocca variant. The update will probably not be listed until the South African operator that owned the variant tests the latest firmware and verify that all is ok.

  

I’m not very patient and decided to test it myself. It turns out, it is possible to change the product code of your device using a software tool called [Nemesis Service Suite (NSS)](http://www.b-phreaks.co.uk/index.php?main_page=page_2)

  

WARNING!!! -  Proceed at your own risk!

  

Certain product codes also mean differences in physical hardware and using the wrong firmware-hardware combination can spell doom for your device!

  

Instructions (modified from <http://www.vigay.com/pda/e90/>):

  
  

  
1. Backup your phone using the Backup tool on Nokia PC Suite.
  
2. Download and install NSS from [Nemesis Service Suite (NSS)](http://www.b-phreaks.co.uk/index.php?main_page=page_2)
  
3. Use the default settings when prompted during install.
  
4. Once installed, close Nokia Application Updater and Nokia PC Suite and run NSS.
  
5. Ensure your E90 USB mode is set to 'PC Suite' and connect your E90 to your PC via the USB cable.
  
6. Run the NSS application. When it loads, click on the **Scan for new device** icon (far right on the toolbar). This should connect to the phone.
  
7. Click on the **Phone Info** tab in NSS.
  
8. Now click on the button which says **Scan** (under Actions)
  
9. Once the phone has been found, click on the **Read** button in the **Production Data Edit** box. The various fields should be filled in automatically.
  
10. Click on **Enable** to the right of the the **Product Code** field.
  
11. Select a valid code from the list below. I used 0550013.
  
12. Enter this code into the **Product Code** field, tick the box, then click on **Write**.
  
13. You can now run the standard Nokia software update program and it should now offer you the new update. (Point of no return)
  

  
  

Phone Model Model Number & Description Product Code   
E90-1 RA-6 EURO A Red 0514979   
E90-1 RA-6 Light SWAP APAC 0515607   
E90-1 RA-6 Light SWAP Philippines 0515610   
E90-1 RA-6 APAC E RED 0515907   
E90-1 RA-5 CUST. TRX EURO A EUR 0523234   
E90-1 RA-6 EURO A Mocca 0533332   
E90-1 RA-6 EURO F1 Mocca South Africa 0544294   
E90-1 RA-6 EURO B Mocca 0544295   
E90-1 RA-6 EURO D Mocca 0544297   
E90-1 RA-6 EURO E Mocca 0544351   
E90-1 RA-6 EURO E Mocca ALS ON 0544353   
E90-1 RA-6 EURO G Mocca French 0544354   
E90-1 RA-6 EURO F Mocca ALS ON 0544355   
E90-1 RA-6 EURO H Mocca 0544356   
E90-1 RA-6 EURO H1 MOCCA 0544357   
E90-1 RA-6 EURO I MOCCA 0544380   
E90-1 RA-6 EURO K MOCCA 0544383   
E90-1 RA-6 EURO M MOCCA 0544384   
E90-1 RA-6 EURO N Russian MOCCA 0544388   
E90-1 RA-6 EURO N Ukraine MOCCA 0544393   
E90-1 RA-6 EURO N Moldova/Belarus MOCCA 0544400   
E90-1 RA-6 EURO N1 MOCCA 0544402   
E90-1 RA-6 EURO O MOCCA 0544403   
E90-1 RA-6 EURO S MOCCA 0544405   
E90-1 RA-6 EURO P MOCCA 0544406   
E90-1 RA-6 APAC C MOCCA HongKong 0544472   
E90-1 RA-6 APAC D MOCCA Singapore 0544485   
E90-1 RA-6 APAC D MOCCA Indonesia 0544486   
E90-1 RA-6 APAC E MOCCA Australia, NZ 0544487   
E90-1 RA-6 APAC E MOCCA 0544489   
E90-1 RA-6 APAC E MOCCA India 0544491   
E90-1 RA-6 APAC F MOCCA Thai 0544496   
E90-1 RA-6 Light SWAP EU-General 0545219   
E90-1 RA-6 EURO C Mocca 0545807   
E90-1 RA-6 EURO F1 Red South Africa 0545983   
E90-1 RA-6 EURO B RED 0545986   
E90-1 RA-6 EURO C RED 0545988   
E90-1 RA-6 EURO E RED 0545990   
E90-1 RA-6 EURO G RED 0545991   
E90-1 RA-6 EURO H1 RED 0545993   
E90-1 RA-6 EURO N RED 0545995   
E90-1 RA-6 EURO O RED 0545997   
E90-1 RA-6 EURO P RED 0545999   
E90-1 RA-6 EURO P1 RED 0546000   
E90-1 RA-6 APAC E RED India 0546002   
E90-1 RA-6 APAC D RED 0546003   
E90-1 RA-6 APAC D RED Indonesia 0546004   
E90-1 RA-6 EURO P1 MOCCA 0546119   
E90-1 RA-6 APAC G MOCCA 0546372   
E90-1 RA-6 EURO L Mocca 0546435   
E90-1 RA-6 EURO Q Mocca 0546436   
E90-1 RA-6 EURO R Mocca 0546437   
E90-1 RA-6 EURO D Red 0546493   
E90-1 RA-6 EURO J Mocca 0546526   
E90-1 RA-6 EURO J1 Mocca 0546527   
E90-1 RA-6 EURO A Mocca SWAP 0548238   
E90-1 RA-6 EURO E Mocca SWAP 0548246   
E90-1 RA-6 EURO G Mocca French SWAP 0548248   
E90-1 RA-6 EURO H Mocca SWAP 0548250   
E90-1 RA-6 EURO H1 MOCCA SWAP 0548251   
E90-1 RA-6 EURO I MOCCA SWAP 0548253   
E90-1 RA-6 EURO J Mocca SWAP 0548256   
E90-1 RA-6 EURO J1 Mocca SWAP 0548257   
E90-1 RA-6 EURO K MOCCA SWAP 0548258   
E90-1 RA-6 EURO L Mocca SWAP 0548259   
E90-1 RA-6 EURO M MOCCA SWAP 0548260   
E90-1 RA-6 EURO N Russian MOCCA SWAP 0548261   
E90-1 RA-6 EURO N Ukraine MOCCA SWAP 0548262   
E90-1 RA-6 EURO O MOCCA SWAP 0548263   
E90-1 RA-6 EURO S MOCCA SWAP 0548264   
E90-1 RA-6 EURO P MOCCA SWAP 0548266   
E90-1 RA-6 EURO A Red SWAP 0548268   
E90-1 RA-6 EURO B RED SWAP 0548269   
E90-1 RA-6 EURO E RED SWAP 0548270   
E90-1 RA-6 EURO G RED SWAP 0548271   
E90-1 RA-6 EURO N RED SWAP 0548272   
E90-1 RA-6 EURO H1 RED SWAP 0548273   
E90-1 RA-6 EURO O RED SWAP 0548274   
E90-1 RA-6 EURO P RED SWAP 0548275   
E90-1 RA-6 EURO B Mocca SWAP 0548290   
E90-1 RA-6 EURO F1 Mocca 0548314   
E90-1 RA-6 EURO F2 Mocca French 0548316   
E90-1 RA-6 EURO F1 Red 0548318   
E90-1 RA-6 EURO F2 RED 0548321   
E90-1 RA-6 EURO H Red 0548578   
E90-1 RA-6 EURO H Red SWAP 0548817   
E90-1 RA-6 EURO N1 Red 0549441   
E90-1 RA-6 EURO F1 SWAP Mocca South Africa 0550013   
E90-1 RA-6 EURO F1 SWAP Red South Africa 0550014   
E90-1 RA-6 EURO J Red 0550193   
E90-1 RA-6 CV CZ Mocca 0550303   
E90-1 RA-6 CV CZ Red 0550304   
E90-1 RA-6 South Africa Country Variant Mocca 0550676   
E90-1 RA-6 Switzerland Country Variant Mocca 0550677   
E90-1 RA-6 Globe Operator Variant Mocca 0550771   
E90-1 RA-6 Smart Operator Variant Mocca 0550773   
E90-1 RA-6 Smart Operator Variant Red 0550776   
E90-1 RA-6 Globe Operator Variant Red 0550778   
E90-1 RA-6 APAC G RED 0550811   
E90-1 RA-6 Light SWAP Taiwan 0550843   
E90-1 RA-6 APAC E RED Australia & NZ 0551005   
E90-1 RA-6 APAC F RED 0551006   
E90-1 RA-6 Vodafone Global Mocca 0551392   
E90-1 RA-6 T-Mobile Global Mocca 0551433   
E90-1 RA-6 CTR Swisscom Mocca 0551773   
E90-1 RA-6 CTR Elisa Finland Mocca 0551805   
E90-1 RA-6 CTR Elisa Finland Red 0551807   
E90-1 RA-6 CTR Sonera SurfPort 4.0 SimL Mocca 0551867   
E90-1 RA-6 CTR Sonera SurfPort 4.0 SimL Red 0551868   
E90-1 RA-6 CTR Vodacom Mocca 0551870   
E90-1 RA-6 CTR T-Mobile CZ Mocca 0551919   
E90-1 RA-6 CTR T-Mobile CZ Red 0551920   
E90-1 RA-6 CTR T-Mobile SK Mocca 0551921   
E90-1 RA-6 CTR T-Mobile GV Austria Mocca 0551947   
E90-1 RA-6 EURO G RED Native FRANCE 0552044   
E90-1 RA-6 EURO G Mocca Native FRANCE 0552045   
E90-1 RA-6 EURO L Red 0552046   
E90-1 RA-6 CTR 3IT Mocca 0552159   
E90-1 RA-6 CTR Vodafone Greece Mocca 0552258   
E90-1 RA-6 CTR Vodafone CZ Mocca 0552389   
E90-1 RA-6 CTR Vodafone Hungary Mocca 0552391   
E90-1 RA-6 CTR Pannon Hungary Mocca 0552392   
E90-1 RA-6 CTR Vodafone UK Mocca 0552396   
E90-1 RA-6 CTR UK country variant Mocca 0552464   
E90-1 RA-6 CTR T-Mobile DE Mocca 0552540   
E90-1 RA-6 CTR Australian Country Variant Mocc 0552625   
E90-1 RA-6 CTR E-Plus Mocca 0552633   
E90-1 RA-6 EURO J1 Red 0552742   
E90-1 RA-6 EURO Q Red 0552919   
E90-1 RA-6 EURO R Red 0552920   
E90-1 RA-6 CTR Vodafone PT Mocca 0553021   
E90-1 RA-6 CTR Vodafone Germany Mocca 0553173   
E90-1 RA-6 CTR Telenor SE Mocca 0553188   
E90-1 RA-6 CTR T-Mobile Hungary Mocca 0553273   
E90-1 RA-6 CTR ERA Mocca 0553341   
E90-1 RA-6 CTR O2 UK Mocca 0553342   
E90-1 RA-6 CTR Vodafone New Zealand Mocca 0553345   
E90-1 RA-6 EURO F RED ALS ON 0553614   
E90-1 RA-6 CTR Russia Country Variant Mocca 0553827   
E90-1 RA-6 CTR Russia Country Variant Red 0553828   
E90-1 RA-6 CTR Ukraine Country Variant Mocca 0553829   
E90-1 RA-6 CTR Belarus-Moldova CV Mocca 0553830   
E90-1 RA-6 CTR Mobilkom Mocca 0553834   
E90-1 RA-6 CTR movistar Mocca 0553841   
E90-1 RA-6 CTR Swisscom FR Mocca 0553934   
E90-1 RA-6 CTR Switzerland CV FR Mocca 0553935   
E90-1 RA-6 CTR Switzerland CV FR Red 0553936   
E90-1 RA-6 CTR H3G Austria Mocca 0553959   
E90-1 RA-6 CTR TIM Italy Mocca 0553973   
E90-1 RA-6 CTR O2 DE Mocca 0554006   
E90-1 RA-6 CTR Movistar Venezuela Mocca 0554040   
E90-1 RA-6 CTR Vodafone Romania Mocca 0554387   
E90-1 RA-6 CTR Mobitel Si Mocca 0554455   
E90-1 RA-6 CTR Vodafone Spain Mocca 0554456   
E90-1 RA-6 CTR Vodafone NL Mocca 0554499   
E90-1 RA-6 CTR Switzerland CV DE Red 0554527   
E90-1 RA-6 CTR Telenor Norway Mocca 0554676   
E90-1 RA-6 CTR ONE Mocca 0555423   
E90-1 RA-6 CTR Ukraine Country Variant Red 0555469   
E90-1 RA-6 EURO E RED ALS ON 0555475   
E90-1 RA-6 CTR T-Mobile GV Croatia Mocca 0555558   
E90-1 RA-6 CTR Sonofon RED 0555561   
E90-1 RA-6 CTR CIS Country Variant Mocca 0555562   
E90-1 RA-6 CTR Sonofon Mocca 0555661   
E90-1 RA-6 CTR Vodafone Ireland Mocca 0555921   
E90-1 RA-6 VIPnet VF live! Business GV Croatia 0555961   
E90-1 RA-6 CTR Germany Country Variant 0556252   
E90-1 RA-6 CTR T-Mobile Hungary Red 0556892   
E90-1 RA-6 CTR PLAY MOCCA 0556904   
E90-1 RA-6 CTR Croatia CV Mocca 0557554   
E90-1 RA-6 CTR Croatia CV Red 0557564   
E90-1 RA-6 Light SWAP APAC 2 0557600   
E90-1 RA-6 Light SWAP Philippines 2 0557601   
E90-1 RA-6 Light SWAP EU-General 2 0557602   
E90-1 RA-6 CTR MegaSync Mocca 0558068   
E90-1 RA-6 CTR TMN Mocca 0558688   
E90-1 RA-6 CTR Telefonica O2 CZ Mocca 0559197   
E90-1 RA-6 CTR 3IT RED 0559503   
E90-1 RA-6 EURO B Black 0561335   
E90-1 RA-6 CTR Polkomtel MOCCA 0561604   
E90-1 RA-6 EURO M Red 0561983   
E90-1 RA-6 APAC D BLACK 0562297   
E90-1 RA-6 APAC D BLACK Indonesia 0562298   
E90-1 RA-6 APAC G BLACK 0562299   
E90-1 RA-6 APAC E BLACK Australia 0562300   
E90-1 RA-6 APAC E BLACK Philippines 0562301   
E90-1 RA-6 APAC E BLACK 0562303   
E90-1 RA-6 APAC F BLACK Thai 0562304   
E90-1 RA-6 EURO A BLACK 0562331   
E90-1 RA-6 EURO I Red 0562633   
E90-1 RA-6 EURO P BLACK 0562934   
E90-1 RA-6 CTR Globe BLACK 0563096   
E90-1 RA-6 CTR Smart Operator Variant BLACK 0563099   
E90-1 RA-6 EURO E BLACK ALS 0563420   
E90-1 RA-6 EURO N BLACK Russian 0563421   
E90-1 RA-6 APAC E MOCCA Bangladesh 0564090   
E90-1 RA-6 APAC E RED Bangladesh 0564091   
E90-1 RA-6 APAC E BLACK BANGLADESH 0564092   
E90-1 RA-6 EURO C Black 0564681   
E90-1 RA-6 EURO E BLACK 0564683   
E90-1 RA-6 EURO G BLACK Native FRANCE 0564684   
E90-1 RA-6 EURO G BLACK FRANCE 0564686   
E90-1 RA-6 EURO H Black 0564687   
E90-1 RA-6 EURO H1 Black 0564688   
E90-1 RA-6 EURO M Black 0564689   
E90-1 RA-6 EURO O Black 0564690   
E90-1 RA-6 EURO F1 BLACK South-Africa 0564742   
E90-1 RA-6 EURO I BLACK 0564743   
E90-1 RA-6 EURO J BLACK 0564744   
E90-1 RA-6 EURO J1 BLACK 0564745   
E90-1 RA-6 EURO L BLACK 0564746   
E90-1 RA-6 EURO P1 BLACK 0564747   
E90-1 RA-6 EURO R BLACK 0565919   
E90-1 RA-6 CTR South Africa ZA CV Black 0566769   
E90-1 RA-6 EURO Q BLACK 0566823   
E90-1 RA-6 EURO F BLACK 0566827   
E90-1 RA-6 CTR TIM IT V2 CU Black P1675 0570568

[Original post](https://ysfk.blogspot.com/2009/08/force-update-of-your-nokia-e90-firmware.html)

#howto #software #devices #legacy-blogger 