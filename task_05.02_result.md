# 05. Task 02 - ICMPv6 echo unicast addresess on iotlab-m3 (default route) [PASSED]
## Captured stdout call

```
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271554 --list saclay,m3,1 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271554 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-9.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  6  HWaddr: 26:85  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: A6:51:FA:B5:22:0D:A6:85 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::a451:fab5:220d:a685  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff0d:a685
          
          Statistics for Layer 2
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 86
            TX succeeded 2 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 128
            TX succeeded 2 errors 0

> ifconfig 6 add beef::1/64
ifconfig 6 add beef::1/64
success: added beef::1/64 to interface 6
> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-1.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  6  HWaddr: 11:92  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: A6:05:7B:E5:C5:1E:11:92 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::a405:7be5:c51e:1192  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff1e:1192
          
          Statistics for Layer 2
            RX packets 3  bytes 129
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 3  bytes 192
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ifconfig 6 add affe::1/120
ifconfig 6 add affe::1/120
success: added affe::1/120 to interface 6
> nib route add 6 :: fe80::a405:7be5:c51e:1192
nib route add 6 :: fe80::a405:7be5:c51e:1192
> nib route add 6 :: fe80::a451:fab5:220d:a685
nib route add 6 :: fe80::a451:fab5:220d:a685
> ping6 beef::1 -c 100 -i 300 -s 1024 -W 1000
ping6 beef::1 -c 100 -i 300 -s 1024 -W 1000
1032 bytes from beef::1: icmp_seq=0 ttl=64 rssi=-46 dBm time=148.332 ms
1032 bytes from beef::1: icmp_seq=1 ttl=64 rssi=-46 dBm time=147.219 ms
1032 bytes from beef::1: icmp_seq=2 ttl=64 rssi=-46 dBm time=159.414 ms
1032 bytes from beef::1: icmp_seq=3 ttl=64 rssi=-46 dBm time=140.499 ms
1032 bytes from beef::1: icmp_seq=4 ttl=64 rssi=-46 dBm time=150.762 ms
1032 bytes from beef::1: icmp_seq=5 ttl=64 rssi=-46 dBm time=148.187 ms
1032 bytes from beef::1: icmp_seq=6 ttl=64 rssi=-46 dBm time=151.698 ms
1032 bytes from beef::1: icmp_seq=8 ttl=64 rssi=-46 dBm time=147.542 ms
1032 bytes from beef::1: icmp_seq=9 ttl=64 rssi=-46 dBm time=161.707 ms
1032 bytes from beef::1: icmp_seq=10 ttl=64 rssi=-46 dBm time=150.770 ms
1032 bytes from beef::1: icmp_seq=11 ttl=64 rssi=-46 dBm time=159.410 ms
1032 bytes from beef::1: icmp_seq=12 ttl=64 rssi=-46 dBm time=138.284 ms
1032 bytes from beef::1: icmp_seq=13 ttl=64 rssi=-46 dBm time=144.037 ms
1032 bytes from beef::1: icmp_seq=14 ttl=64 rssi=-46 dBm time=148.197 ms
1032 bytes from beef::1: icmp_seq=15 ttl=64 rssi=-46 dBm time=160.362 ms
1032 bytes from beef::1: icmp_seq=16 ttl=64 rssi=-46 dBm time=137.069 ms
1032 bytes from beef::1: icmp_seq=17 ttl=64 rssi=-46 dBm time=140.582 ms
1032 bytes from beef::1: icmp_seq=18 ttl=64 rssi=-46 dBm time=137.715 ms
1032 bytes from beef::1: icmp_seq=19 ttl=64 rssi=-46 dBm time=143.074 ms
1032 bytes from beef::1: icmp_seq=20 ttl=64 rssi=-46 dBm time=151.074 ms
1032 bytes from beef::1: icmp_seq=21 ttl=64 rssi=-46 dBm time=147.218 ms
1032 bytes from beef::1: icmp_seq=22 ttl=64 rssi=-46 dBm time=156.831 ms
1032 bytes from beef::1: icmp_seq=23 ttl=64 rssi=-46 dBm time=149.954 ms
1032 bytes from beef::1: icmp_seq=24 ttl=64 rssi=-46 dBm time=136.360 ms
1032 bytes from beef::1: icmp_seq=25 ttl=64 rssi=-46 dBm time=142.754 ms
1032 bytes from beef::1: icmp_seq=26 ttl=64 rssi=-46 dBm time=160.044 ms
1032 bytes from beef::1: icmp_seq=27 ttl=64 rssi=-46 dBm time=138.914 ms
1032 bytes from beef::1: icmp_seq=28 ttl=64 rssi=-46 dBm time=142.769 ms
1032 bytes from beef::1: icmp_seq=29 ttl=64 rssi=-46 dBm time=151.696 ms
1032 bytes from beef::1: icmp_seq=30 ttl=64 rssi=-46 dBm time=156.201 ms
1032 bytes from beef::1: icmp_seq=31 ttl=64 rssi=-46 dBm time=151.721 ms
1032 bytes from beef::1: icmp_seq=32 ttl=64 rssi=-46 dBm time=158.768 ms
1032 bytes from beef::1: icmp_seq=33 ttl=64 rssi=-46 dBm time=151.088 ms
1032 bytes from beef::1: icmp_seq=34 ttl=64 rssi=-46 dBm time=140.833 ms
1032 bytes from beef::1: icmp_seq=35 ttl=64 rssi=-46 dBm time=147.232 ms
1032 bytes from beef::1: icmp_seq=36 ttl=64 rssi=-46 dBm time=147.233 ms
1032 bytes from beef::1: icmp_seq=37 ttl=64 rssi=-46 dBm time=158.744 ms
1032 bytes from beef::1: icmp_seq=38 ttl=64 rssi=-46 dBm time=148.521 ms
1032 bytes from beef::1: icmp_seq=39 ttl=64 rssi=-46 dBm time=147.873 ms
1032 bytes from beef::1: icmp_seq=40 ttl=64 rssi=-46 dBm time=160.058 ms
1032 bytes from beef::1: icmp_seq=41 ttl=64 rssi=-46 dBm time=143.379 ms
1032 bytes from beef::1: icmp_seq=42 ttl=64 rssi=-46 dBm time=156.204 ms
1032 bytes from beef::1: icmp_seq=43 ttl=64 rssi=-46 dBm time=140.849 ms
1032 bytes from beef::1: icmp_seq=44 ttl=64 rssi=-46 dBm time=148.515 ms
1032 bytes from beef::1: icmp_seq=45 ttl=64 rssi=-46 dBm time=145.308 ms
1032 bytes from beef::1: icmp_seq=46 ttl=64 rssi=-46 dBm time=152.353 ms
1032 bytes from beef::1: icmp_seq=47 ttl=64 rssi=-46 dBm time=151.102 ms
1032 bytes from beef::1: icmp_seq=48 ttl=64 rssi=-46 dBm time=143.409 ms
1032 bytes from beef::1: icmp_seq=49 ttl=64 rssi=-46 dBm time=160.041 ms
1032 bytes from beef::1: icmp_seq=50 ttl=64 rssi=-46 dBm time=140.194 ms
1032 bytes from beef::1: icmp_seq=51 ttl=64 rssi=-46 dBm time=136.408 ms
1032 bytes from beef::1: icmp_seq=52 ttl=64 rssi=-46 dBm time=149.793 ms
1032 bytes from beef::1: icmp_seq=53 ttl=64 rssi=-46 dBm time=142.779 ms
1032 bytes from beef::1: icmp_seq=54 ttl=64 rssi=-46 dBm time=144.343 ms
1032 bytes from beef::1: icmp_seq=55 ttl=64 rssi=-46 dBm time=156.224 ms
1032 bytes from beef::1: icmp_seq=56 ttl=64 rssi=-46 dBm time=148.528 ms
1032 bytes from beef::1: icmp_seq=57 ttl=64 rssi=-46 dBm time=137.001 ms
1032 bytes from beef::1: icmp_seq=58 ttl=64 rssi=-46 dBm time=152.987 ms
1032 bytes from beef::1: icmp_seq=59 ttl=64 rssi=-46 dBm time=152.352 ms
1032 bytes from beef::1: icmp_seq=60 ttl=64 rssi=-46 dBm time=155.031 ms
1032 bytes from beef::1: icmp_seq=61 ttl=64 rssi=-46 dBm time=144.672 ms
1032 bytes from beef::1: icmp_seq=62 ttl=64 rssi=-46 dBm time=137.657 ms
1032 bytes from beef::1: icmp_seq=63 ttl=64 rssi=-46 dBm time=140.836 ms
1032 bytes from beef::1: icmp_seq=64 ttl=64 rssi=-46 dBm time=147.889 ms
1032 bytes from beef::1: icmp_seq=65 ttl=64 rssi=-46 dBm time=157.457 ms
1032 bytes from beef::1: icmp_seq=66 ttl=64 rssi=-46 dBm time=136.362 ms
1032 bytes from beef::1: icmp_seq=67 ttl=64 rssi=-46 dBm time=149.168 ms
1032 bytes from beef::1: icmp_seq=68 ttl=64 rssi=-46 dBm time=136.345 ms
1032 bytes from beef::1: icmp_seq=69 ttl=64 rssi=-46 dBm time=151.726 ms
1032 bytes from beef::1: icmp_seq=70 ttl=64 rssi=-46 dBm time=158.758 ms
1032 bytes from beef::1: icmp_seq=71 ttl=64 rssi=-46 dBm time=145.315 ms
1032 bytes from beef::1: icmp_seq=72 ttl=64 rssi=-46 dBm time=144.681 ms
1032 bytes from beef::1: icmp_seq=73 ttl=64 rssi=-46 dBm time=155.565 ms
1032 bytes from beef::1: icmp_seq=74 ttl=64 rssi=-46 dBm time=152.351 ms
1032 bytes from beef::1: icmp_seq=75 ttl=64 rssi=-46 dBm time=155.549 ms
1032 bytes from beef::1: icmp_seq=76 ttl=64 rssi=-46 dBm time=136.985 ms
1032 bytes from beef::1: icmp_seq=77 ttl=64 rssi=-46 dBm time=152.984 ms
1032 bytes from beef::1: icmp_seq=78 ttl=64 rssi=-46 dBm time=147.866 ms
1032 bytes from beef::1: icmp_seq=79 ttl=64 rssi=-46 dBm time=159.541 ms
1032 bytes from beef::1: icmp_seq=80 ttl=64 rssi=-46 dBm time=147.348 ms
1032 bytes from beef::1: icmp_seq=81 ttl=64 rssi=-46 dBm time=149.139 ms
1032 bytes from beef::1: icmp_seq=82 ttl=64 rssi=-46 dBm time=145.938 ms
1032 bytes from beef::1: icmp_seq=83 ttl=64 rssi=-46 dBm time=149.137 ms
1032 bytes from beef::1: icmp_seq=84 ttl=64 rssi=-46 dBm time=163.376 ms
1032 bytes from beef::1: icmp_seq=85 ttl=64 rssi=-46 dBm time=131.264 ms
1032 bytes from beef::1: icmp_seq=86 ttl=64 rssi=-46 dBm time=141.474 ms
1032 bytes from beef::1: icmp_seq=87 ttl=64 rssi=-46 dBm time=144.674 ms
1032 bytes from beef::1: icmp_seq=88 ttl=64 rssi=-46 dBm time=142.130 ms
1032 bytes from beef::1: icmp_seq=89 ttl=64 rssi=-46 dBm time=160.159 ms
1032 bytes from beef::1: icmp_seq=90 ttl=64 rssi=-46 dBm time=152.985 ms
1032 bytes from beef::1: icmp_seq=91 ttl=64 rssi=-46 dBm time=156.846 ms
1032 bytes from beef::1: icmp_seq=92 ttl=64 rssi=-46 dBm time=142.753 ms
1032 bytes from beef::1: icmp_seq=93 ttl=64 rssi=-46 dBm time=153.661 ms
1032 bytes from beef::1: icmp_seq=94 ttl=64 rssi=-46 dBm time=139.693 ms
1032 bytes from beef::1: icmp_seq=95 ttl=64 rssi=-46 dBm time=144.048 ms
1032 bytes from beef::1: icmp_seq=96 ttl=64 rssi=-46 dBm time=138.290 ms
1032 bytes from beef::1: icmp_seq=97 ttl=64 rssi=-46 dBm time=138.944 ms
1032 bytes from beef::1: icmp_seq=98 ttl=64 rssi=-46 dBm time=151.713 ms
1032 bytes from beef::1: icmp_seq=99 ttl=64 rssi=-46 dBm time=149.152 ms

--- beef::1 PING statistics ---
100 packets transmitted, 99 packets received, 1% packet loss
round-trip min/avg/max = 131.264/148.201/163.376 ms
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 2440
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 2680
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> 
```

