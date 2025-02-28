<!--
date: '2005-09-19'
published: true
slug: 2005-09-iws-2005-monday-afternoon-notes_19
time_to_read: 5
title: IWS 2005 Monday Afternoon notes
-->

MOCCA: Summary of think-tank  
Focus is on Asian developing market, particularly India and China.  
Debate between whether investment into existing technology in rural sector of mobile market will have better returns than further urban investment into new technology.  
Debate on whether voice or data services are more important in rural areas.  
Debate on what a rural area is? Low density population?  
  
Mobile Handover Strategies, A. Slingerland  
Mobility management scheme supports multiple strategies and smartly selects best strategy which will improve QoS  
Application requirements; latency, loss, re-ordering  
Context issues; link layer hints, network support nodes, load  
Hierarchical Mobile IP  
Static handover is sub-optimal  
  
Distributed QoS control Arch for latency sensitive applications, Mahbubul Alam  
QoS, multi-layer challenge  
Basic Challengers: BW, Delay and Jitter  
Arch challenges: Scalabity, Resource management, Robustness against traffic fluctuations, Billing, Security  
Seamless security needs to be included in design along with QoS.  
Security can provide QoS, e.g. ipsec, however not scalable  
QoS routing policy  
  
M. Canales (mcanales@unizar.es)  
Shortest path not necessarily QoS, resource utilisation at MAC layer more important  
New QoS metric based on Mac resources  
Distruitbuted   
Basis: AOMDV  
ADHOC MAC protocol  
Destination selects best path after receiving multipath info / metric  
Simulation: Event driven simulator in c++ ( Adhoc MAC + modified aomdv+path bandwidth calc algorithm)  
Best effort strategy: AODV  
QoS metric based strategy QoS Routing, AOMDV  
  
Distributed Admission Control Algorithm  
IEEE 802.11e EDCA QoS Concept  
  
QoS relate to RT and non-Rt services, which may have contrasting delays and reliability requirements, flexible QoS management required.  
Proposed system based on ITU-R  
Vertical and horizontal handover  

[Original post](https://ysfk.blogspot.com/2005/09/iws-2005-monday-afternoon-notes_19.html)

#legacy-blogger 