# 07. Task 01 - ICMPv6 echo on iotlab-m3 with three hops (static route) [PASSED]
## Captured stdout setup

```
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271560 --list saclay,m3,1 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271560 --list saclay,m3,2 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271560 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271560 --list saclay,m3,12 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-1.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 11:92  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
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
            RX packets 9  bytes 387
            TX packets 5 (Multicast: 5)  bytes 215
            TX succeeded 5 errors 0
          Statistics for IPv6
            RX packets 9  bytes 576
            TX packets 5 (Multicast: 5)  bytes 320
            TX succeeded 5 errors 0

> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-2.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 17:32  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: EE:19:4D:E3:D3:BA:17:32 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::ec19:4de3:d3ba:1732  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ffba:1732
          
          Statistics for Layer 2
            RX packets 7  bytes 301
            TX packets 4 (Multicast: 4)  bytes 172
            TX succeeded 4 errors 0
          Statistics for IPv6
            RX packets 7  bytes 448
            TX packets 4 (Multicast: 4)  bytes 256
            TX succeeded 4 errors 0

> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-9.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 26:85  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
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
            RX packets 4  bytes 172
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 4  bytes 256
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-12.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 36:2B  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: E6:2E:CE:92:CA:67:B6:2B 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::e42e:ce92:ca67:b62b  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff67:b62b
          
          Statistics for Layer 2
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 86
            TX succeeded 2 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 128
            TX succeeded 2 errors 0

> ifconfig 5 add beef::1/64
ifconfig 5 add beef::1/64
success: added beef::1/64 to interface 5
> ifconfig 5 add affe::1/64
ifconfig 5 add affe::1/64
success: added affe::1/64 to interface 5
> nib route add 5 affe::1/64 fe80::ec19:4de3:d3ba:1732
nib route add 5 affe::1/64 fe80::ec19:4de3:d3ba:1732
> nib route add 5 affe::1/64 fe80::a451:fab5:220d:a685
nib route add 5 affe::1/64 fe80::a451:fab5:220d:a685
> nib route add 5 beef::1/64 fe80::a405:7be5:c51e:1192
nib route add 5 beef::1/64 fe80::a405:7be5:c51e:1192
> nib route add 5 affe::1/64 fe80::e42e:ce92:ca67:b62b
nib route add 5 affe::1/64 fe80::e42e:ce92:ca67:b62b
> nib route add 5 beef::1/64 fe80::ec19:4de3:d3ba:1732
nib route add 5 beef::1/64 fe80::ec19:4de3:d3ba:1732
> nib route add 5 beef::1/64 fe80::a451:fab5:220d:a685
nib route add 5 beef::1/64 fe80::a451:fab5:220d:a685
> 
```

## Captured stdout call

```
ping6 affe::1 -c 100 -i 100 -s 50 -W 1000
ping6 affe::1 -c 100 -i 100 -s 50 -W 1000
58 bytes from affe::1: icmp_seq=0 ttl=62 rssi=-43 dBm time=36.855 ms
58 bytes from affe::1: icmp_seq=1 ttl=62 rssi=-43 dBm time=37.798 ms
58 bytes from affe::1: icmp_seq=2 ttl=62 rssi=-43 dBm time=44.332 ms
58 bytes from affe::1: icmp_seq=3 ttl=62 rssi=-43 dBm time=46.439 ms
58 bytes from affe::1: icmp_seq=4 ttl=62 rssi=-43 dBm time=42.918 ms
58 bytes from affe::1: icmp_seq=6 ttl=62 rssi=-43 dBm time=38.456 ms
58 bytes from affe::1: icmp_seq=7 ttl=62 rssi=-43 dBm time=40.051 ms
58 bytes from affe::1: icmp_seq=8 ttl=62 rssi=-43 dBm time=41.010 ms
58 bytes from affe::1: icmp_seq=9 ttl=62 rssi=-43 dBm time=40.039 ms
58 bytes from affe::1: icmp_seq=10 ttl=62 rssi=-43 dBm time=42.599 ms
58 bytes from affe::1: icmp_seq=11 ttl=62 rssi=-43 dBm time=39.411 ms
58 bytes from affe::1: icmp_seq=12 ttl=62 rssi=-43 dBm time=42.279 ms
58 bytes from affe::1: icmp_seq=13 ttl=62 rssi=-43 dBm time=43.885 ms
58 bytes from affe::1: icmp_seq=14 ttl=62 rssi=-43 dBm time=42.605 ms
58 bytes from affe::1: icmp_seq=15 ttl=62 rssi=-43 dBm time=42.918 ms
58 bytes from affe::1: icmp_seq=16 ttl=62 rssi=-43 dBm time=43.565 ms
58 bytes from affe::1: icmp_seq=17 ttl=62 rssi=-43 dBm time=40.372 ms
58 bytes from affe::1: icmp_seq=18 ttl=62 rssi=-43 dBm time=38.451 ms
58 bytes from affe::1: icmp_seq=19 ttl=62 rssi=-43 dBm time=40.038 ms
58 bytes from affe::1: icmp_seq=20 ttl=62 rssi=-43 dBm time=39.091 ms
58 bytes from affe::1: icmp_seq=21 ttl=62 rssi=-43 dBm time=42.272 ms
58 bytes from affe::1: icmp_seq=22 ttl=62 rssi=-43 dBm time=45.159 ms
58 bytes from affe::1: icmp_seq=23 ttl=62 rssi=-43 dBm time=41.325 ms
58 bytes from affe::1: icmp_seq=24 ttl=62 rssi=-43 dBm time=41.959 ms
58 bytes from affe::1: icmp_seq=25 ttl=62 rssi=-43 dBm time=43.239 ms
58 bytes from affe::1: icmp_seq=26 ttl=62 rssi=-43 dBm time=43.558 ms
58 bytes from affe::1: icmp_seq=27 ttl=62 rssi=-43 dBm time=41.005 ms
58 bytes from affe::1: icmp_seq=28 ttl=62 rssi=-43 dBm time=42.278 ms
58 bytes from affe::1: icmp_seq=29 ttl=62 rssi=-43 dBm time=39.085 ms
58 bytes from affe::1: icmp_seq=30 ttl=62 rssi=-43 dBm time=41.958 ms
58 bytes from affe::1: icmp_seq=31 ttl=62 rssi=-43 dBm time=43.239 ms
58 bytes from affe::1: icmp_seq=32 ttl=62 rssi=-43 dBm time=43.231 ms
58 bytes from affe::1: icmp_seq=33 ttl=62 rssi=-43 dBm time=42.919 ms
58 bytes from affe::1: icmp_seq=34 ttl=62 rssi=-43 dBm time=40.365 ms
58 bytes from affe::1: icmp_seq=35 ttl=62 rssi=-43 dBm time=39.405 ms
58 bytes from affe::1: icmp_seq=36 ttl=62 rssi=-43 dBm time=38.765 ms
58 bytes from affe::1: icmp_seq=37 ttl=62 rssi=-43 dBm time=39.717 ms
58 bytes from affe::1: icmp_seq=38 ttl=62 rssi=-43 dBm time=41.659 ms
58 bytes from affe::1: icmp_seq=39 ttl=62 rssi=-43 dBm time=40.692 ms
58 bytes from affe::1: icmp_seq=40 ttl=62 rssi=-43 dBm time=42.599 ms
58 bytes from affe::1: icmp_seq=41 ttl=62 rssi=-43 dBm time=44.192 ms
58 bytes from affe::1: icmp_seq=42 ttl=62 rssi=-43 dBm time=40.038 ms
58 bytes from affe::1: icmp_seq=43 ttl=62 rssi=-43 dBm time=37.491 ms
58 bytes from affe::1: icmp_seq=44 ttl=62 rssi=-43 dBm time=38.765 ms
58 bytes from affe::1: icmp_seq=45 ttl=62 rssi=-43 dBm time=42.599 ms
58 bytes from affe::1: icmp_seq=46 ttl=62 rssi=-43 dBm time=41.964 ms
58 bytes from affe::1: icmp_seq=47 ttl=62 rssi=-43 dBm time=43.879 ms
58 bytes from affe::1: icmp_seq=48 ttl=62 rssi=-43 dBm time=40.684 ms
58 bytes from affe::1: icmp_seq=49 ttl=62 rssi=-43 dBm time=43.559 ms
58 bytes from affe::1: icmp_seq=50 ttl=62 rssi=-43 dBm time=44.198 ms
58 bytes from affe::1: icmp_seq=51 ttl=62 rssi=-43 dBm time=41.639 ms
58 bytes from affe::1: icmp_seq=52 ttl=62 rssi=-43 dBm time=45.799 ms
58 bytes from affe::1: icmp_seq=53 ttl=62 rssi=-43 dBm time=43.879 ms
58 bytes from affe::1: icmp_seq=54 ttl=62 rssi=-43 dBm time=42.280 ms
58 bytes from affe::1: icmp_seq=55 ttl=62 rssi=-43 dBm time=39.725 ms
58 bytes from affe::1: icmp_seq=56 ttl=62 rssi=-43 dBm time=43.565 ms
58 bytes from affe::1: icmp_seq=57 ttl=62 rssi=-43 dBm time=42.299 ms
58 bytes from affe::1: icmp_seq=58 ttl=62 rssi=-43 dBm time=38.766 ms
58 bytes from affe::1: icmp_seq=59 ttl=62 rssi=-43 dBm time=43.239 ms
58 bytes from affe::1: icmp_seq=60 ttl=62 rssi=-43 dBm time=43.568 ms
58 bytes from affe::1: icmp_seq=61 ttl=62 rssi=-43 dBm time=37.490 ms
58 bytes from affe::1: icmp_seq=62 ttl=62 rssi=-43 dBm time=40.680 ms
58 bytes from affe::1: icmp_seq=63 ttl=62 rssi=-43 dBm time=41.318 ms
58 bytes from affe::1: icmp_seq=64 ttl=62 rssi=-43 dBm time=43.880 ms
58 bytes from affe::1: icmp_seq=65 ttl=62 rssi=-43 dBm time=42.279 ms
58 bytes from affe::1: icmp_seq=66 ttl=62 rssi=-43 dBm time=39.725 ms
58 bytes from affe::1: icmp_seq=67 ttl=62 rssi=-43 dBm time=40.679 ms
58 bytes from affe::1: icmp_seq=68 ttl=62 rssi=-43 dBm time=41.959 ms
58 bytes from affe::1: icmp_seq=69 ttl=62 rssi=-43 dBm time=43.239 ms
58 bytes from affe::1: icmp_seq=70 ttl=62 rssi=-43 dBm time=41.645 ms
58 bytes from affe::1: icmp_seq=71 ttl=62 rssi=-43 dBm time=42.619 ms
58 bytes from affe::1: icmp_seq=72 ttl=62 rssi=-43 dBm time=42.270 ms
58 bytes from affe::1: icmp_seq=73 ttl=62 rssi=-43 dBm time=42.919 ms
58 bytes from affe::1: icmp_seq=74 ttl=62 rssi=-43 dBm time=41.319 ms
58 bytes from affe::1: icmp_seq=75 ttl=62 rssi=-43 dBm time=43.239 ms
58 bytes from affe::1: icmp_seq=76 ttl=62 rssi=-43 dBm time=40.691 ms
58 bytes from affe::1: icmp_seq=77 ttl=62 rssi=-43 dBm time=39.410 ms
58 bytes from affe::1: icmp_seq=78 ttl=62 rssi=-43 dBm time=41.647 ms
58 bytes from affe::1: icmp_seq=79 ttl=62 rssi=-43 dBm time=41.319 ms
58 bytes from affe::1: icmp_seq=80 ttl=62 rssi=-43 dBm time=41.006 ms
58 bytes from affe::1: icmp_seq=81 ttl=62 rssi=-43 dBm time=39.733 ms
58 bytes from affe::1: icmp_seq=82 ttl=62 rssi=-43 dBm time=36.851 ms
58 bytes from affe::1: icmp_seq=83 ttl=62 rssi=-43 dBm time=43.879 ms
58 bytes from affe::1: icmp_seq=84 ttl=62 rssi=-43 dBm time=42.606 ms
58 bytes from affe::1: icmp_seq=85 ttl=62 rssi=-43 dBm time=38.445 ms
58 bytes from affe::1: icmp_seq=86 ttl=62 rssi=-43 dBm time=39.720 ms
58 bytes from affe::1: icmp_seq=87 ttl=62 rssi=-43 dBm time=40.685 ms
58 bytes from affe::1: icmp_seq=88 ttl=62 rssi=-43 dBm time=44.204 ms
58 bytes from affe::1: icmp_seq=89 ttl=62 rssi=-43 dBm time=39.719 ms
58 bytes from affe::1: icmp_seq=90 ttl=62 rssi=-43 dBm time=43.238 ms
58 bytes from affe::1: icmp_seq=91 ttl=62 rssi=-43 dBm time=41.331 ms
58 bytes from affe::1: icmp_seq=92 ttl=62 rssi=-43 dBm time=42.599 ms
58 bytes from affe::1: icmp_seq=93 ttl=62 rssi=-43 dBm time=44.199 ms
58 bytes from affe::1: icmp_seq=94 ttl=62 rssi=-43 dBm time=46.431 ms
58 bytes from affe::1: icmp_seq=95 ttl=62 rssi=-43 dBm time=43.239 ms
58 bytes from affe::1: icmp_seq=96 ttl=62 rssi=-43 dBm time=40.679 ms
58 bytes from affe::1: icmp_seq=97 ttl=62 rssi=-43 dBm time=43.558 ms
58 bytes from affe::1: icmp_seq=98 ttl=62 rssi=-43 dBm time=38.758 ms
58 bytes from affe::1: icmp_seq=99 ttl=62 rssi=-43 dBm time=38.131 ms

--- affe::1 PING statistics ---
100 packets transmitted, 99 packets received, 1% packet loss
round-trip min/avg/max = 36.851/41.585/46.439 ms
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 440
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 440
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 440
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 440
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> 
```

