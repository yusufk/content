<!--
date: '2005-09-21'
published: true
slug: 2005-09-iws2005-wednesday
time_to_read: 5
title: IWS2005 Wednesday
-->

**IWS2005 Thursday**  
Broadband Rollout and the role of wireless, Steffen Ring, Director Motorola  
IEEE802 has 3 categories, Wire line 802.1, 802.3, 802.21 , Wireless 802.11.802.15, 802.16, 802.20 and tech advisory 802.18, 802.19  
  
Enhanced Data rate, 802.11n WLan approx 200+ Mb/s in testing may be able to handle 1000’s of calls and possibly uncompressed video  
  
New mobile extensions to WiMax, 802.16e  
Mesh networks 802.11s  
  
802.11a 5GHz 54Mb/s PHY based on OFDM  
802.11v 2.4GHz 11Mb/s PHY based on DSSS  
802.11d  
802.11f Support for roaming  
802.11h European 802.11a  
802.11i Security  
802.11n High Throughput  
  
802.16 Single Carrier MAC/PHY layer 11-66GHz  
802.16e Mobile Broadband Wireless Access  
WiMax based on 802.16 and 802.16e  
  
<http://www.wirelessman.org/tge/index.html>  
  
DVB-H as Broadband Access Technology, Reza Tadayoni, CICT, Tech Univ Denmark,  
Mobile and Broadcast Convergence  
Inband – UMTS and GPRS e.g mibiTV  
Hybrid – DVB-H, DMB (Korea), ISDB-T (Japan), MediaFLO (Qualcomm, US)  
DVB-H up to 11Mb/s  
  
BREAD project, Broadband access for all in Europe  
Mention made of African Cantenna project  
  
Rate Switching in 802.11e, dude from Toshiba  
Currently, it is impossible to change the transmission rate during a burst because of Block ACK  
4 algorithms proposed to solve the problem  
1) link adaptation algorithm for Block ACK  
Change and compare ratio of change of rate within a burst  
2) Reduce the burst size  
3)  
4) A tail data packet with a higher rate is attached in every burst  
  
Problem: 802.11 suffers from downlink throughput degradation when uplink traffic increases, cause: AP must transmit all downlink traffic and acquires the channel with the same probability as a single station, therefore to solve the prob, a new scheme is needed.  
Solution: In the proposed scheme the AP has a single CSMA/CA function, this lowers prob of collision.  
Proposed Scheme compared to DCF and Multiple CSMA/CA  
After 26 station Multiple CSMA throughput drops  
DCF and proposed scheme seem better, DCF drops off at 50  
  
Current Frame burst handling of frame errors not efficient  
Dymanic Queue prioritizing proposed.  
Results show that after 30 stations, throughput decreases more in normal round robin than the proposed queue prioritization

[Original post](https://ysfk.blogspot.com/2005/09/iws2005-wednesday.html)

#wifi #telecoms #engineering #legacy-blogger 