<p align="center">

</p>


<h2>Video Demonstration</h2>

- ### [YouTube: Day 12 Life of a Packet MAC Addresses](https://www.youtube.com/watch?v=rj6F-HQ_MOE)

<h2>Environments and Technologies Used</h2>

- Jeremy's IT Lab Youtube Channel
- Cisco Packet Tracer
  

  
<h2>Operating Systems Used </h2>

- Cisco IOS


<h2>Step-by-Step</h2>
PC1 pings PC4

- Source/Destination MAC at PC1 -> SW1 segment: 00D0.BA11.1111/0000.01aa.aaaa 

- Source/Destination MAC at SW -> R1 segment: 00D0.BA11.1111/0000.01aa.aaaa

- Source/Destination MAC at R1 -> R2 segment: 0000.01bb.bbbb/0000.01cc.cccc

- Source/Destination MAC at R2 -> R3 segment: 0000.01dd.dddd/0000.01ee.eeee

- Source Destination MAC at R3 -> SW2 segment: 0000.01ff.ffff/0001.c78a.be19

- Source/Destination MAC at SW2 -> P4 segment: 0001.c78a.be01/000C.8544.4444

PC1 pings PC3

- Source Destination MAC at PC1 -> SW1 segment: 00D0.BA11.1111/0001.6479.c001

- Source Destination MAC at SW1 -> PC3 segment: 
