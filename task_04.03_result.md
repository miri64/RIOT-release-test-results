# 04. Task 03 - ICMPv6 echo with large payload [PASSED]
## Captured stdout call

```
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271540 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271540 --list saclay,m3,12 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-12.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  6  HWaddr: 36:2B  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
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

> ifconfig 6 set channel 26
ifconfig 6 set channel 26
success: set channel on interface 6 to 26
> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-9.saclay.iot-lab.info:20000' 


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
            RX packets 3  bytes 129
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 3  bytes 192
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ifconfig 6 set channel 26
ifconfig 6 set channel 26
success: set channel on interface 6 to 26
> ping6 fe80::e42e:ce92:ca67:b62b -c 500 -i 300 -s 1024 -W 1000
ping6 fe80::e42e:ce92:ca67:b62b -c 500 -i 300 -s 1024 -W 1000
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=0 ttl=64 rssi=-43 dBm time=141.860 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=2 ttl=64 rssi=-43 dBm time=144.729 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=3 ttl=64 rssi=-43 dBm time=139.280 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=4 ttl=64 rssi=-43 dBm time=140.880 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=5 ttl=64 rssi=-43 dBm time=139.921 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=6 ttl=64 rssi=-43 dBm time=140.249 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=7 ttl=64 rssi=-43 dBm time=136.407 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=8 ttl=64 rssi=-43 dBm time=138.321 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=9 ttl=64 rssi=-43 dBm time=153.032 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=10 ttl=64 rssi=-43 dBm time=134.176 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=11 ttl=64 rssi=-43 dBm time=136.089 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=12 ttl=64 rssi=-43 dBm time=144.413 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=13 ttl=64 rssi=-43 dBm time=133.516 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=14 ttl=64 rssi=-43 dBm time=133.846 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=15 ttl=64 rssi=-43 dBm time=143.756 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=16 ttl=64 rssi=-43 dBm time=145.685 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=17 ttl=64 rssi=-43 dBm time=139.619 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=18 ttl=64 rssi=-43 dBm time=134.161 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=19 ttl=64 rssi=-43 dBm time=132.876 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=20 ttl=64 rssi=-43 dBm time=135.126 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=22 ttl=64 rssi=-43 dBm time=132.577 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=23 ttl=64 rssi=-43 dBm time=142.161 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=24 ttl=64 rssi=-43 dBm time=138.345 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=25 ttl=64 rssi=-43 dBm time=135.782 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=26 ttl=64 rssi=-43 dBm time=132.581 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=27 ttl=64 rssi=-43 dBm time=138.001 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=28 ttl=64 rssi=-43 dBm time=139.615 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=29 ttl=64 rssi=-43 dBm time=145.714 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=30 ttl=64 rssi=-43 dBm time=137.381 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=31 ttl=64 rssi=-43 dBm time=136.723 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=32 ttl=64 rssi=-43 dBm time=144.405 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=33 ttl=64 rssi=-43 dBm time=149.539 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=34 ttl=64 rssi=-43 dBm time=141.866 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=35 ttl=64 rssi=-43 dBm time=147.283 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=36 ttl=64 rssi=-43 dBm time=134.503 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=37 ttl=64 rssi=-43 dBm time=125.858 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=38 ttl=64 rssi=-43 dBm time=132.894 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=39 ttl=64 rssi=-43 dBm time=134.510 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=40 ttl=64 rssi=-43 dBm time=139.307 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=41 ttl=64 rssi=-43 dBm time=132.884 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=42 ttl=64 rssi=-43 dBm time=139.292 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=43 ttl=64 rssi=-43 dBm time=146.966 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=44 ttl=64 rssi=-43 dBm time=142.502 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=45 ttl=64 rssi=-43 dBm time=131.622 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=46 ttl=64 rssi=-43 dBm time=141.527 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=47 ttl=64 rssi=-43 dBm time=132.900 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=48 ttl=64 rssi=-43 dBm time=144.650 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=49 ttl=64 rssi=-43 dBm time=141.197 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=50 ttl=64 rssi=-43 dBm time=145.661 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=51 ttl=64 rssi=-43 dBm time=141.203 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=52 ttl=64 rssi=-43 dBm time=134.509 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=53 ttl=64 rssi=-43 dBm time=144.101 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=54 ttl=64 rssi=-43 dBm time=138.636 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=55 ttl=64 rssi=-43 dBm time=134.798 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=56 ttl=64 rssi=-43 dBm time=141.821 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=57 ttl=64 rssi=-43 dBm time=139.915 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=58 ttl=64 rssi=-43 dBm time=135.772 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=59 ttl=64 rssi=-43 dBm time=133.838 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=60 ttl=64 rssi=-43 dBm time=144.107 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=61 ttl=64 rssi=-43 dBm time=142.796 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=62 ttl=64 rssi=-43 dBm time=136.417 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=63 ttl=64 rssi=-43 dBm time=141.837 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=64 ttl=64 rssi=-43 dBm time=143.766 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=65 ttl=64 rssi=-43 dBm time=141.525 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=66 ttl=64 rssi=-43 dBm time=140.878 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=67 ttl=64 rssi=-43 dBm time=137.396 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=68 ttl=64 rssi=-43 dBm time=130.664 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=69 ttl=64 rssi=-43 dBm time=142.513 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=70 ttl=64 rssi=-43 dBm time=138.342 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=71 ttl=64 rssi=-43 dBm time=146.643 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=72 ttl=64 rssi=-43 dBm time=132.587 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=73 ttl=64 rssi=-43 dBm time=141.853 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=74 ttl=64 rssi=-43 dBm time=137.374 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=75 ttl=64 rssi=-43 dBm time=142.157 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=76 ttl=64 rssi=-43 dBm time=142.147 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=77 ttl=64 rssi=-43 dBm time=145.684 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=78 ttl=64 rssi=-43 dBm time=140.236 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=79 ttl=64 rssi=-43 dBm time=142.803 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=80 ttl=64 rssi=-43 dBm time=134.482 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=81 ttl=64 rssi=-43 dBm time=139.300 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=82 ttl=64 rssi=-43 dBm time=142.150 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=83 ttl=64 rssi=-43 dBm time=135.773 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=84 ttl=64 rssi=-43 dBm time=137.995 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=85 ttl=64 rssi=-43 dBm time=140.555 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=86 ttl=64 rssi=-43 dBm time=149.203 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=87 ttl=64 rssi=-43 dBm time=141.197 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=88 ttl=64 rssi=-43 dBm time=138.651 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=89 ttl=64 rssi=-43 dBm time=136.707 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=90 ttl=64 rssi=-43 dBm time=139.916 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=91 ttl=64 rssi=-43 dBm time=143.462 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=92 ttl=64 rssi=-43 dBm time=144.747 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=93 ttl=64 rssi=-43 dBm time=131.926 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=94 ttl=64 rssi=-43 dBm time=137.374 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=95 ttl=64 rssi=-43 dBm time=134.476 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=96 ttl=64 rssi=-43 dBm time=140.556 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=97 ttl=64 rssi=-43 dBm time=140.867 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=98 ttl=64 rssi=-43 dBm time=135.779 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=99 ttl=64 rssi=-43 dBm time=143.131 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=100 ttl=64 rssi=-43 dBm time=143.749 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=101 ttl=64 rssi=-43 dBm time=155.333 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=102 ttl=64 rssi=-43 dBm time=136.412 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=103 ttl=64 rssi=-43 dBm time=129.683 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=104 ttl=64 rssi=-43 dBm time=141.516 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=105 ttl=64 rssi=-43 dBm time=136.396 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=106 ttl=64 rssi=-43 dBm time=138.638 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=107 ttl=64 rssi=-43 dBm time=138.331 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=108 ttl=64 rssi=-43 dBm time=145.478 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=109 ttl=64 rssi=-43 dBm time=138.651 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=110 ttl=64 rssi=-43 dBm time=144.410 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=111 ttl=64 rssi=-43 dBm time=140.579 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=112 ttl=64 rssi=-43 dBm time=139.263 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=113 ttl=64 rssi=-43 dBm time=146.340 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=114 ttl=64 rssi=-43 dBm time=143.447 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=115 ttl=64 rssi=-43 dBm time=141.502 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=116 ttl=64 rssi=-43 dBm time=149.537 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=117 ttl=64 rssi=-43 dBm time=129.396 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=118 ttl=64 rssi=-43 dBm time=125.873 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=119 ttl=64 rssi=-43 dBm time=133.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=120 ttl=64 rssi=-43 dBm time=139.939 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=121 ttl=64 rssi=-43 dBm time=130.663 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=122 ttl=64 rssi=-43 dBm time=128.118 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=123 ttl=64 rssi=-43 dBm time=130.317 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=124 ttl=64 rssi=-43 dBm time=142.506 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=125 ttl=64 rssi=-43 dBm time=137.037 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=126 ttl=64 rssi=-43 dBm time=132.557 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=127 ttl=64 rssi=-43 dBm time=137.374 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=128 ttl=64 rssi=-43 dBm time=143.771 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=129 ttl=64 rssi=-43 dBm time=135.778 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=130 ttl=64 rssi=-43 dBm time=133.853 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=131 ttl=64 rssi=-43 dBm time=142.485 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=132 ttl=64 rssi=-43 dBm time=139.597 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=133 ttl=64 rssi=-43 dBm time=141.538 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=134 ttl=64 rssi=-43 dBm time=134.820 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=135 ttl=64 rssi=-43 dBm time=138.012 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=136 ttl=64 rssi=-43 dBm time=140.541 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=137 ttl=64 rssi=-43 dBm time=149.210 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=138 ttl=64 rssi=-43 dBm time=141.516 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=139 ttl=64 rssi=-43 dBm time=141.857 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=140 ttl=64 rssi=-43 dBm time=137.997 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=141 ttl=64 rssi=-43 dBm time=138.004 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=142 ttl=64 rssi=-43 dBm time=139.916 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=143 ttl=64 rssi=-43 dBm time=140.218 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=144 ttl=64 rssi=-43 dBm time=146.644 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=145 ttl=64 rssi=-43 dBm time=141.854 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=146 ttl=64 rssi=-43 dBm time=138.008 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=147 ttl=64 rssi=-43 dBm time=147.910 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=148 ttl=64 rssi=-43 dBm time=145.051 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=149 ttl=64 rssi=-43 dBm time=133.844 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=150 ttl=64 rssi=-43 dBm time=150.493 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=151 ttl=64 rssi=-43 dBm time=130.333 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=152 ttl=64 rssi=-43 dBm time=141.213 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=153 ttl=64 rssi=-43 dBm time=138.316 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=154 ttl=64 rssi=-43 dBm time=140.555 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=155 ttl=64 rssi=-43 dBm time=148.884 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=156 ttl=64 rssi=-43 dBm time=138.628 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=157 ttl=64 rssi=-43 dBm time=142.782 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=158 ttl=64 rssi=-43 dBm time=141.213 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=159 ttl=64 rssi=-43 dBm time=135.149 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=160 ttl=64 rssi=-43 dBm time=143.465 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=161 ttl=64 rssi=-43 dBm time=133.887 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=162 ttl=64 rssi=-43 dBm time=134.804 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=163 ttl=64 rssi=-43 dBm time=133.533 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=164 ttl=64 rssi=-43 dBm time=146.963 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=165 ttl=64 rssi=-43 dBm time=137.036 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=166 ttl=64 rssi=-43 dBm time=136.724 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=167 ttl=64 rssi=-43 dBm time=140.251 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=168 ttl=64 rssi=-43 dBm time=148.230 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=169 ttl=64 rssi=-43 dBm time=146.002 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=170 ttl=64 rssi=-43 dBm time=132.891 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=171 ttl=64 rssi=-43 dBm time=138.975 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=172 ttl=64 rssi=-43 dBm time=134.497 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=173 ttl=64 rssi=-43 dBm time=138.666 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=174 ttl=64 rssi=-43 dBm time=143.457 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=175 ttl=64 rssi=-43 dBm time=141.516 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=176 ttl=64 rssi=-43 dBm time=136.108 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=177 ttl=64 rssi=-43 dBm time=143.465 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=178 ttl=64 rssi=-43 dBm time=134.798 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=179 ttl=64 rssi=-43 dBm time=133.516 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=180 ttl=64 rssi=-43 dBm time=143.133 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=181 ttl=64 rssi=-43 dBm time=142.477 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=182 ttl=64 rssi=-43 dBm time=142.499 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=183 ttl=64 rssi=-43 dBm time=137.661 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=184 ttl=64 rssi=-43 dBm time=140.884 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=185 ttl=64 rssi=-43 dBm time=140.563 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=186 ttl=64 rssi=-43 dBm time=139.942 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=187 ttl=64 rssi=-43 dBm time=142.165 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=188 ttl=64 rssi=-43 dBm time=138.317 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=189 ttl=64 rssi=-43 dBm time=137.038 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=190 ttl=64 rssi=-43 dBm time=153.373 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=191 ttl=64 rssi=-43 dBm time=134.797 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=192 ttl=64 rssi=-43 dBm time=136.415 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=193 ttl=64 rssi=-43 dBm time=137.073 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=194 ttl=64 rssi=-43 dBm time=138.303 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=195 ttl=64 rssi=-43 dBm time=147.931 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=196 ttl=64 rssi=-43 dBm time=142.808 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=197 ttl=64 rssi=-43 dBm time=136.069 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=198 ttl=64 rssi=-43 dBm time=135.459 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=199 ttl=64 rssi=-43 dBm time=131.935 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=200 ttl=64 rssi=-43 dBm time=139.582 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=201 ttl=64 rssi=-43 dBm time=144.405 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=202 ttl=64 rssi=-43 dBm time=143.435 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=203 ttl=64 rssi=-43 dBm time=134.811 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=204 ttl=64 rssi=-43 dBm time=137.376 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=205 ttl=64 rssi=-43 dBm time=133.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=206 ttl=64 rssi=-43 dBm time=138.340 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=207 ttl=64 rssi=-43 dBm time=135.458 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=208 ttl=64 rssi=-43 dBm time=137.036 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=209 ttl=64 rssi=-43 dBm time=137.364 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=210 ttl=64 rssi=-43 dBm time=142.818 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=211 ttl=64 rssi=-43 dBm time=130.338 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=212 ttl=64 rssi=-43 dBm time=137.705 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=213 ttl=64 rssi=-43 dBm time=136.120 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=214 ttl=64 rssi=-43 dBm time=149.842 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=215 ttl=64 rssi=-43 dBm time=135.756 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=216 ttl=64 rssi=-43 dBm time=133.836 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=217 ttl=64 rssi=-43 dBm time=144.717 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=218 ttl=64 rssi=-43 dBm time=146.965 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=219 ttl=64 rssi=-43 dBm time=142.483 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=220 ttl=64 rssi=-43 dBm time=147.597 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=221 ttl=64 rssi=-43 dBm time=144.415 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=222 ttl=64 rssi=-43 dBm time=126.820 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=223 ttl=64 rssi=-43 dBm time=130.340 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=224 ttl=64 rssi=-43 dBm time=131.635 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=225 ttl=64 rssi=-43 dBm time=136.398 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=226 ttl=64 rssi=-43 dBm time=138.038 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=227 ttl=64 rssi=-43 dBm time=137.374 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=228 ttl=64 rssi=-43 dBm time=140.251 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=229 ttl=64 rssi=-43 dBm time=146.970 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=230 ttl=64 rssi=-43 dBm time=133.205 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=231 ttl=64 rssi=-43 dBm time=133.847 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=232 ttl=64 rssi=-43 dBm time=143.769 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=233 ttl=64 rssi=-43 dBm time=130.653 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=234 ttl=64 rssi=-43 dBm time=140.237 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=235 ttl=64 rssi=-43 dBm time=140.558 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=236 ttl=64 rssi=-43 dBm time=149.221 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=237 ttl=64 rssi=-43 dBm time=140.222 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=238 ttl=64 rssi=-43 dBm time=138.333 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=239 ttl=64 rssi=-43 dBm time=141.225 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=240 ttl=64 rssi=-43 dBm time=134.796 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=241 ttl=64 rssi=-43 dBm time=133.850 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=242 ttl=64 rssi=-43 dBm time=145.035 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=243 ttl=64 rssi=-43 dBm time=138.330 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=244 ttl=64 rssi=-43 dBm time=135.444 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=245 ttl=64 rssi=-43 dBm time=141.838 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=246 ttl=64 rssi=-43 dBm time=135.452 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=247 ttl=64 rssi=-43 dBm time=144.722 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=249 ttl=64 rssi=-43 dBm time=142.482 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=250 ttl=64 rssi=-43 dBm time=147.929 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=251 ttl=64 rssi=-43 dBm time=133.505 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=252 ttl=64 rssi=-43 dBm time=143.760 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=253 ttl=64 rssi=-43 dBm time=134.478 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=254 ttl=64 rssi=-43 dBm time=133.846 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=255 ttl=64 rssi=-43 dBm time=145.025 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=256 ttl=64 rssi=-43 dBm time=137.379 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=257 ttl=64 rssi=-43 dBm time=137.991 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=258 ttl=64 rssi=-43 dBm time=137.361 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=259 ttl=64 rssi=-43 dBm time=138.987 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=260 ttl=64 rssi=-43 dBm time=143.453 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=261 ttl=64 rssi=-43 dBm time=143.443 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=262 ttl=64 rssi=-43 dBm time=144.725 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=263 ttl=64 rssi=-43 dBm time=139.611 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=264 ttl=64 rssi=-43 dBm time=139.917 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=265 ttl=64 rssi=-43 dBm time=148.914 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=266 ttl=64 rssi=-43 dBm time=134.179 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=267 ttl=64 rssi=-43 dBm time=138.019 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=268 ttl=64 rssi=-43 dBm time=134.841 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=269 ttl=64 rssi=-43 dBm time=140.861 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=270 ttl=64 rssi=-43 dBm time=137.684 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=271 ttl=64 rssi=-43 dBm time=146.316 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=272 ttl=64 rssi=-43 dBm time=138.956 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=273 ttl=64 rssi=-43 dBm time=139.602 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=274 ttl=64 rssi=-43 dBm time=143.742 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=275 ttl=64 rssi=-43 dBm time=137.053 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=276 ttl=64 rssi=-43 dBm time=141.501 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=277 ttl=64 rssi=-43 dBm time=146.340 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=278 ttl=64 rssi=-43 dBm time=134.185 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=279 ttl=64 rssi=-43 dBm time=137.692 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=280 ttl=64 rssi=-43 dBm time=131.939 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=281 ttl=64 rssi=-43 dBm time=141.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=282 ttl=64 rssi=-43 dBm time=141.524 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=283 ttl=64 rssi=-43 dBm time=142.162 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=284 ttl=64 rssi=-43 dBm time=136.083 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=285 ttl=64 rssi=-43 dBm time=145.057 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=286 ttl=64 rssi=-43 dBm time=132.887 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=287 ttl=64 rssi=-43 dBm time=150.469 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=288 ttl=64 rssi=-43 dBm time=130.652 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=289 ttl=64 rssi=-43 dBm time=134.483 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=290 ttl=64 rssi=-43 dBm time=138.984 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=291 ttl=64 rssi=-43 dBm time=130.641 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=292 ttl=64 rssi=-43 dBm time=144.427 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=293 ttl=64 rssi=-43 dBm time=138.357 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=294 ttl=64 rssi=-43 dBm time=137.342 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=295 ttl=64 rssi=-43 dBm time=147.921 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=296 ttl=64 rssi=-43 dBm time=134.812 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=297 ttl=64 rssi=-43 dBm time=143.777 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=298 ttl=64 rssi=-43 dBm time=139.619 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=299 ttl=64 rssi=-43 dBm time=141.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=300 ttl=64 rssi=-43 dBm time=146.636 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=301 ttl=64 rssi=-43 dBm time=144.082 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=302 ttl=64 rssi=-43 dBm time=144.061 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=303 ttl=64 rssi=-43 dBm time=129.057 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=304 ttl=64 rssi=-43 dBm time=128.396 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=305 ttl=64 rssi=-43 dBm time=131.301 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=306 ttl=64 rssi=-43 dBm time=139.291 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=307 ttl=64 rssi=-43 dBm time=135.788 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=308 ttl=64 rssi=-43 dBm time=129.355 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=309 ttl=64 rssi=-43 dBm time=132.242 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=310 ttl=64 rssi=-43 dBm time=138.638 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=311 ttl=64 rssi=-43 dBm time=132.269 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=312 ttl=64 rssi=-43 dBm time=137.828 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=313 ttl=64 rssi=-43 dBm time=138.622 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=314 ttl=64 rssi=-43 dBm time=133.867 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=315 ttl=64 rssi=-43 dBm time=149.202 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=316 ttl=64 rssi=-43 dBm time=133.191 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=317 ttl=64 rssi=-43 dBm time=140.905 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=318 ttl=64 rssi=-43 dBm time=137.057 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=319 ttl=64 rssi=-43 dBm time=143.756 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=320 ttl=64 rssi=-43 dBm time=133.868 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=321 ttl=64 rssi=-43 dBm time=135.422 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=322 ttl=64 rssi=-43 dBm time=140.564 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=323 ttl=64 rssi=-43 dBm time=148.595 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=324 ttl=64 rssi=-43 dBm time=144.413 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=325 ttl=64 rssi=-43 dBm time=136.410 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=326 ttl=64 rssi=-43 dBm time=145.652 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=327 ttl=64 rssi=-43 dBm time=134.824 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=328 ttl=64 rssi=-43 dBm time=142.165 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=329 ttl=64 rssi=-43 dBm time=139.603 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=330 ttl=64 rssi=-43 dBm time=143.142 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=331 ttl=64 rssi=-43 dBm time=143.438 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=332 ttl=64 rssi=-43 dBm time=139.597 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=333 ttl=64 rssi=-43 dBm time=144.738 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=334 ttl=64 rssi=-43 dBm time=145.997 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=335 ttl=64 rssi=-43 dBm time=137.667 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=336 ttl=64 rssi=-43 dBm time=141.532 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=337 ttl=64 rssi=-43 dBm time=141.220 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=338 ttl=64 rssi=-43 dBm time=138.344 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=339 ttl=64 rssi=-43 dBm time=135.438 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=340 ttl=64 rssi=-43 dBm time=143.122 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=341 ttl=64 rssi=-43 dBm time=147.275 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=342 ttl=64 rssi=-43 dBm time=139.299 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=343 ttl=64 rssi=-43 dBm time=142.514 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=344 ttl=64 rssi=-43 dBm time=142.483 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=345 ttl=64 rssi=-43 dBm time=142.805 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=346 ttl=64 rssi=-43 dBm time=131.322 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=347 ttl=64 rssi=-43 dBm time=133.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=348 ttl=64 rssi=-43 dBm time=133.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=349 ttl=64 rssi=-43 dBm time=143.118 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=350 ttl=64 rssi=-43 dBm time=138.323 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=351 ttl=64 rssi=-43 dBm time=135.774 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=352 ttl=64 rssi=-43 dBm time=146.337 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=353 ttl=64 rssi=-43 dBm time=137.357 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=354 ttl=64 rssi=-43 dBm time=145.361 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=355 ttl=64 rssi=-43 dBm time=142.833 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=356 ttl=64 rssi=-43 dBm time=138.338 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=357 ttl=64 rssi=-43 dBm time=140.901 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=358 ttl=64 rssi=-43 dBm time=133.214 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=359 ttl=64 rssi=-43 dBm time=140.900 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=360 ttl=64 rssi=-43 dBm time=138.941 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=361 ttl=64 rssi=-43 dBm time=139.916 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=362 ttl=64 rssi=-43 dBm time=140.893 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=363 ttl=64 rssi=-43 dBm time=136.724 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=364 ttl=64 rssi=-43 dBm time=138.009 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=365 ttl=64 rssi=-43 dBm time=129.390 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=366 ttl=64 rssi=-43 dBm time=146.005 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=367 ttl=64 rssi=-43 dBm time=146.968 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=368 ttl=64 rssi=-43 dBm time=137.982 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=369 ttl=64 rssi=-43 dBm time=136.733 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=370 ttl=64 rssi=-43 dBm time=139.922 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=371 ttl=64 rssi=-43 dBm time=142.476 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=372 ttl=64 rssi=-43 dBm time=139.290 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=373 ttl=64 rssi=-43 dBm time=148.565 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=374 ttl=64 rssi=-43 dBm time=132.589 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=375 ttl=64 rssi=-43 dBm time=142.477 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=376 ttl=64 rssi=-43 dBm time=144.740 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=377 ttl=64 rssi=-43 dBm time=139.294 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=378 ttl=64 rssi=-43 dBm time=136.082 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=379 ttl=64 rssi=-43 dBm time=138.636 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=380 ttl=64 rssi=-43 dBm time=143.458 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=381 ttl=64 rssi=-43 dBm time=137.051 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=382 ttl=64 rssi=-43 dBm time=152.706 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=383 ttl=64 rssi=-43 dBm time=139.945 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=384 ttl=64 rssi=-43 dBm time=128.747 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=385 ttl=64 rssi=-43 dBm time=136.396 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=386 ttl=64 rssi=-43 dBm time=137.357 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=387 ttl=64 rssi=-43 dBm time=143.773 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=388 ttl=64 rssi=-43 dBm time=142.617 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=389 ttl=64 rssi=-43 dBm time=135.763 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=390 ttl=64 rssi=-43 dBm time=135.117 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=391 ttl=64 rssi=-43 dBm time=137.676 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=392 ttl=64 rssi=-43 dBm time=140.862 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=393 ttl=64 rssi=-43 dBm time=134.502 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=394 ttl=64 rssi=-43 dBm time=134.815 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=395 ttl=64 rssi=-43 dBm time=146.965 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=396 ttl=64 rssi=-43 dBm time=133.553 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=397 ttl=64 rssi=-43 dBm time=128.115 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=398 ttl=64 rssi=-43 dBm time=138.332 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=399 ttl=64 rssi=-43 dBm time=140.570 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=400 ttl=64 rssi=-43 dBm time=143.769 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=401 ttl=64 rssi=-43 dBm time=135.799 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=402 ttl=64 rssi=-43 dBm time=139.278 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=403 ttl=64 rssi=-43 dBm time=143.138 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=404 ttl=64 rssi=-43 dBm time=146.651 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=405 ttl=64 rssi=-43 dBm time=144.706 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=406 ttl=64 rssi=-43 dBm time=146.323 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=407 ttl=64 rssi=-43 dBm time=143.763 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=408 ttl=64 rssi=-43 dBm time=127.778 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=409 ttl=64 rssi=-43 dBm time=130.014 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=410 ttl=64 rssi=-43 dBm time=134.188 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=411 ttl=64 rssi=-43 dBm time=138.350 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=412 ttl=64 rssi=-43 dBm time=132.556 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=413 ttl=64 rssi=-43 dBm time=136.092 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=414 ttl=64 rssi=-43 dBm time=141.218 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=415 ttl=64 rssi=-43 dBm time=149.524 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=416 ttl=64 rssi=-43 dBm time=133.508 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=417 ttl=64 rssi=-43 dBm time=138.677 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=418 ttl=64 rssi=-43 dBm time=133.850 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=419 ttl=64 rssi=-43 dBm time=135.474 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=420 ttl=64 rssi=-43 dBm time=137.355 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=421 ttl=64 rssi=-43 dBm time=143.436 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=422 ttl=64 rssi=-43 dBm time=148.242 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=423 ttl=64 rssi=-43 dBm time=137.022 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=424 ttl=64 rssi=-43 dBm time=141.535 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=425 ttl=64 rssi=-43 dBm time=137.058 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=426 ttl=64 rssi=-43 dBm time=135.779 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=427 ttl=64 rssi=-43 dBm time=134.813 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=428 ttl=64 rssi=-43 dBm time=146.980 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=429 ttl=64 rssi=-43 dBm time=137.369 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=430 ttl=64 rssi=-43 dBm time=134.492 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=431 ttl=64 rssi=-43 dBm time=140.579 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=432 ttl=64 rssi=-43 dBm time=140.572 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=433 ttl=64 rssi=-43 dBm time=139.273 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=434 ttl=64 rssi=-43 dBm time=137.996 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=435 ttl=64 rssi=-43 dBm time=144.076 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=436 ttl=64 rssi=-43 dBm time=146.978 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=437 ttl=64 rssi=-43 dBm time=131.924 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=438 ttl=64 rssi=-43 dBm time=146.333 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=439 ttl=64 rssi=-43 dBm time=134.173 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=440 ttl=64 rssi=-43 dBm time=132.554 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=441 ttl=64 rssi=-43 dBm time=146.650 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=442 ttl=64 rssi=-43 dBm time=138.334 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=443 ttl=64 rssi=-43 dBm time=136.412 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=444 ttl=64 rssi=-43 dBm time=137.981 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=445 ttl=64 rssi=-43 dBm time=138.331 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=446 ttl=64 rssi=-43 dBm time=142.497 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=447 ttl=64 rssi=-43 dBm time=143.443 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=448 ttl=64 rssi=-43 dBm time=145.989 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=449 ttl=64 rssi=-43 dBm time=139.275 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=450 ttl=64 rssi=-43 dBm time=141.518 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=451 ttl=64 rssi=-43 dBm time=146.343 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=452 ttl=64 rssi=-43 dBm time=133.544 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=453 ttl=64 rssi=-43 dBm time=139.601 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=454 ttl=64 rssi=-43 dBm time=134.477 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=455 ttl=64 rssi=-43 dBm time=140.222 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=456 ttl=64 rssi=-43 dBm time=137.983 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=457 ttl=64 rssi=-43 dBm time=147.621 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=458 ttl=64 rssi=-43 dBm time=138.332 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=459 ttl=64 rssi=-43 dBm time=140.236 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=460 ttl=64 rssi=-43 dBm time=143.115 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=461 ttl=64 rssi=-43 dBm time=137.054 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=462 ttl=64 rssi=-43 dBm time=141.822 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=463 ttl=64 rssi=-43 dBm time=146.341 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=464 ttl=64 rssi=-43 dBm time=133.517 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=465 ttl=64 rssi=-43 dBm time=138.303 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=466 ttl=64 rssi=-43 dBm time=131.637 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=467 ttl=64 rssi=-43 dBm time=140.860 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=468 ttl=64 rssi=-43 dBm time=141.837 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=469 ttl=64 rssi=-43 dBm time=142.818 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=470 ttl=64 rssi=-43 dBm time=134.805 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=471 ttl=64 rssi=-43 dBm time=146.645 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=472 ttl=64 rssi=-43 dBm time=134.174 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=473 ttl=64 rssi=-43 dBm time=146.648 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=474 ttl=64 rssi=-43 dBm time=131.286 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=475 ttl=64 rssi=-43 dBm time=133.858 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=476 ttl=64 rssi=-43 dBm time=138.358 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=477 ttl=64 rssi=-43 dBm time=131.641 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=478 ttl=64 rssi=-43 dBm time=145.053 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=479 ttl=64 rssi=-43 dBm time=139.924 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=480 ttl=64 rssi=-43 dBm time=137.997 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=481 ttl=64 rssi=-43 dBm time=147.282 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=482 ttl=64 rssi=-43 dBm time=135.450 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=483 ttl=64 rssi=-43 dBm time=139.966 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=484 ttl=64 rssi=-43 dBm time=140.883 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=485 ttl=64 rssi=-43 dBm time=144.404 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=486 ttl=64 rssi=-43 dBm time=143.777 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=487 ttl=64 rssi=-43 dBm time=145.364 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=488 ttl=64 rssi=-43 dBm time=144.395 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=489 ttl=64 rssi=-43 dBm time=126.799 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=490 ttl=64 rssi=-43 dBm time=129.355 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=491 ttl=64 rssi=-43 dBm time=132.253 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=492 ttl=64 rssi=-43 dBm time=139.597 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=493 ttl=64 rssi=-43 dBm time=133.842 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=494 ttl=64 rssi=-43 dBm time=130.965 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=495 ttl=64 rssi=-43 dBm time=131.915 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=496 ttl=64 rssi=-43 dBm time=137.694 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=497 ttl=64 rssi=-43 dBm time=131.932 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=498 ttl=64 rssi=-43 dBm time=136.724 ms
1032 bytes from fe80::e42e:ce92:ca67:b62b%6: icmp_seq=499 ttl=64 rssi=-43 dBm time=139.276 ms

--- fe80::e42e:ce92:ca67:b62b PING statistics ---
500 packets transmitted, 497 packets received, 0% packet loss
round-trip min/avg/max = 125.858/139.290/155.333 ms
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 3608
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 2680
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> 
```

