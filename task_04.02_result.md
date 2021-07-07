# 04. Task 02 - ICMPv6 multicast echo with iotlab-m3/samr21-xpro [PASSED]
## Captured stdout call

```
Building application "gnrc_networking" for "samr21-xpro" with MCU "samd21".

   text	   data	    bss	    dec	    hex	filename
  96556	    188	  18988	 115732	  1c414	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/samr21-xpro/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271539 --list saclay,samr21,10 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/samr21-xpro/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271539 --list saclay,m3,1 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-1.saclay.iot-lab.info:20000' 


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
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 86
            TX succeeded 2 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 128
            TX succeeded 2 errors 0

> ifconfig 6 set channel 17
ifconfig 6 set channel 17
success: set channel on interface 6 to 17
> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:samr21-10.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  6  HWaddr: 3C:8D  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: 00:04:25:19:18:01:BC:8D 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::204:2519:1801:bc8d  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff01:bc8d
          
          Statistics for Layer 2
            RX packets 3  bytes 129
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 3  bytes 192
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ifconfig 6 set channel 17
ifconfig 6 set channel 17
success: set channel on interface 6 to 17
> ping6 ff02::1 -c 1000 -i 100 -s 50 -W 1000
ping6 ff02::1 -c 1000 -i 100 -s 50 -W 1000
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=0 ttl=64 rssi=-61 dBm time=9.034 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=1 ttl=64 rssi=-61 dBm time=9.343 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=2 ttl=64 rssi=-61 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=3 ttl=64 rssi=-61 dBm time=10.938 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=4 ttl=64 rssi=-61 dBm time=10.293 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=5 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=6 ttl=64 rssi=-61 dBm time=13.486 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=7 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=8 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=9 ttl=64 rssi=-61 dBm time=12.210 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=10 ttl=64 rssi=-61 dBm time=14.258 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=11 ttl=64 rssi=-61 dBm time=10.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=12 ttl=64 rssi=-61 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=13 ttl=64 rssi=-61 dBm time=13.167 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=14 ttl=64 rssi=-61 dBm time=11.889 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=15 ttl=64 rssi=-61 dBm time=9.035 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=16 ttl=64 rssi=-61 dBm time=21.094 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=17 ttl=64 rssi=-61 dBm time=11.570 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=18 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=19 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=20 ttl=64 rssi=-61 dBm time=10.294 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=21 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=22 ttl=64 rssi=-61 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=23 ttl=64 rssi=-61 dBm time=12.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=24 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=25 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=26 ttl=64 rssi=-61 dBm time=9.986 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=27 ttl=64 rssi=-61 dBm time=13.168 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=28 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=29 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=30 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=34 ttl=64 rssi=-61 dBm time=16.174 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=35 ttl=64 rssi=-61 dBm time=11.571 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=35 ttl=64 rssi=-61 dBm time=20.878 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=36 ttl=64 rssi=-61 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=37 ttl=64 rssi=-60 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=38 ttl=64 rssi=-61 dBm time=13.946 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=39 ttl=64 rssi=-61 dBm time=10.619 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=40 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=41 ttl=64 rssi=-61 dBm time=9.988 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=42 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=43 ttl=64 rssi=-61 dBm time=10.944 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=44 ttl=64 rssi=-61 dBm time=11.889 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=45 ttl=64 rssi=-61 dBm time=9.661 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=46 ttl=64 rssi=-61 dBm time=10.613 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=47 ttl=64 rssi=-61 dBm time=9.667 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=48 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=49 ttl=64 rssi=-61 dBm time=9.348 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=50 ttl=64 rssi=-62 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=51 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=52 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=53 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=54 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=55 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=56 ttl=64 rssi=-61 dBm time=10.294 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=57 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=58 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=59 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=60 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=61 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=62 ttl=64 rssi=-62 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=63 ttl=64 rssi=-61 dBm time=12.355 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=64 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=65 ttl=64 rssi=-62 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=66 ttl=64 rssi=-61 dBm time=12.670 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=67 ttl=64 rssi=-61 dBm time=10.939 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=68 ttl=64 rssi=-61 dBm time=10.305 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=69 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=70 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=71 ttl=64 rssi=-61 dBm time=12.208 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=72 ttl=64 rssi=-61 dBm time=12.209 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=73 ttl=64 rssi=-61 dBm time=13.167 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=74 ttl=64 rssi=-61 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=75 ttl=64 rssi=-62 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=76 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=77 ttl=64 rssi=-61 dBm time=12.848 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=78 ttl=64 rssi=-61 dBm time=12.207 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=79 ttl=64 rssi=-61 dBm time=12.982 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=80 ttl=64 rssi=-61 dBm time=18.549 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=82 ttl=64 rssi=-61 dBm time=12.793 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=83 ttl=64 rssi=-61 dBm time=11.578 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=83 ttl=64 rssi=-61 dBm time=20.945 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=84 ttl=64 rssi=-61 dBm time=9.980 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=85 ttl=64 rssi=-61 dBm time=10.294 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=86 ttl=64 rssi=-61 dBm time=10.613 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=87 ttl=64 rssi=-60 dBm time=12.849 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=88 ttl=64 rssi=-60 dBm time=14.898 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=89 ttl=64 rssi=-61 dBm time=14.896 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=90 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=91 ttl=64 rssi=-61 dBm time=12.989 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=92 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=93 ttl=64 rssi=-61 dBm time=15.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=94 ttl=64 rssi=-61 dBm time=12.210 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=95 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=96 ttl=64 rssi=-61 dBm time=9.348 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=97 ttl=64 rssi=-61 dBm time=12.208 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=98 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=99 ttl=64 rssi=-61 dBm time=16.173 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=100 ttl=64 rssi=-61 dBm time=10.301 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=101 ttl=64 rssi=-61 dBm time=10.613 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=102 ttl=64 rssi=-61 dBm time=9.656 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=103 ttl=64 rssi=-61 dBm time=10.613 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=104 ttl=64 rssi=-61 dBm time=12.849 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=105 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=106 ttl=64 rssi=-61 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=107 ttl=64 rssi=-61 dBm time=12.847 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=108 ttl=64 rssi=-61 dBm time=11.571 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=109 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=110 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=111 ttl=64 rssi=-61 dBm time=15.671 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=112 ttl=64 rssi=-61 dBm time=13.168 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=113 ttl=64 rssi=-61 dBm time=12.210 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=114 ttl=64 rssi=-61 dBm time=13.301 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=115 ttl=64 rssi=-61 dBm time=11.259 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=116 ttl=64 rssi=-61 dBm time=9.661 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=117 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=118 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=119 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=120 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=121 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=122 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=123 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=124 ttl=64 rssi=-61 dBm time=11.890 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=125 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=126 ttl=64 rssi=-61 dBm time=9.656 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=127 ttl=64 rssi=-61 dBm time=10.932 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=128 ttl=64 rssi=-61 dBm time=14.577 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=129 ttl=64 rssi=-61 dBm time=15.536 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=130 ttl=64 rssi=-61 dBm time=11.848 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=131 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=131 ttl=64 rssi=-61 dBm time=21.350 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=132 ttl=64 rssi=-61 dBm time=18.410 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=133 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=133 ttl=64 rssi=-61 dBm time=22.604 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=134 ttl=64 rssi=-61 dBm time=11.263 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=135 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=136 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=137 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=138 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=139 ttl=64 rssi=-61 dBm time=13.940 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=140 ttl=64 rssi=-61 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=141 ttl=64 rssi=-61 dBm time=9.037 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=142 ttl=64 rssi=-61 dBm time=11.086 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=143 ttl=64 rssi=-61 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=144 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=145 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=146 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=147 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=148 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=149 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=150 ttl=64 rssi=-61 dBm time=10.942 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=151 ttl=64 rssi=-61 dBm time=10.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=152 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=153 ttl=64 rssi=-61 dBm time=9.657 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=154 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=155 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=156 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=157 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=158 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=159 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=160 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=161 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=162 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=163 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=164 ttl=64 rssi=-60 dBm time=17.905 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=165 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=166 ttl=64 rssi=-61 dBm time=9.350 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=167 ttl=64 rssi=-61 dBm time=12.983 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=168 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=169 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=170 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=171 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=172 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=173 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=174 ttl=64 rssi=-61 dBm time=10.761 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=175 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=176 ttl=64 rssi=-61 dBm time=16.816 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=177 ttl=64 rssi=-61 dBm time=13.488 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=179 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=180 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=180 ttl=64 rssi=-61 dBm time=20.327 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=181 ttl=64 rssi=-61 dBm time=9.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=182 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=183 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=184 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=185 ttl=64 rssi=-61 dBm time=9.344 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=186 ttl=64 rssi=-61 dBm time=16.311 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=187 ttl=64 rssi=-62 dBm time=9.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=188 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=189 ttl=64 rssi=-61 dBm time=10.621 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=190 ttl=64 rssi=-61 dBm time=10.939 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=191 ttl=64 rssi=-61 dBm time=9.662 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=192 ttl=64 rssi=-61 dBm time=17.913 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=193 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=194 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=195 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=196 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=197 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=198 ttl=64 rssi=-61 dBm time=9.669 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=199 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=200 ttl=64 rssi=-61 dBm time=9.344 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=201 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=202 ttl=64 rssi=-61 dBm time=9.657 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=203 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=204 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=205 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=206 ttl=64 rssi=-61 dBm time=11.259 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=207 ttl=64 rssi=-61 dBm time=9.034 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=208 ttl=64 rssi=-61 dBm time=9.657 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=209 ttl=64 rssi=-61 dBm time=9.669 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=210 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=211 ttl=64 rssi=-61 dBm time=13.952 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=212 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=213 ttl=64 rssi=-62 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=214 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=215 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=216 ttl=64 rssi=-61 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=217 ttl=64 rssi=-61 dBm time=11.706 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=218 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=219 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=220 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=221 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=222 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=223 ttl=64 rssi=-61 dBm time=9.037 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=224 ttl=64 rssi=-61 dBm time=15.219 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=225 ttl=64 rssi=-61 dBm time=14.581 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=227 ttl=64 rssi=-61 dBm time=13.952 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=228 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=228 ttl=64 rssi=-61 dBm time=21.920 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=229 ttl=64 rssi=-61 dBm time=12.850 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=229 ttl=64 rssi=-61 dBm time=22.311 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=230 ttl=64 rssi=-61 dBm time=10.628 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=231 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=232 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=233 ttl=64 rssi=-61 dBm time=9.982 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=234 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=235 ttl=64 rssi=-61 dBm time=11.581 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=236 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=237 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=238 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=239 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=240 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=241 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=242 ttl=64 rssi=-61 dBm time=14.721 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=243 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=244 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=245 ttl=64 rssi=-61 dBm time=11.895 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=246 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=247 ttl=64 rssi=-61 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=248 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=249 ttl=64 rssi=-61 dBm time=9.350 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=250 ttl=64 rssi=-61 dBm time=9.988 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=251 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=252 ttl=64 rssi=-61 dBm time=10.943 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=253 ttl=64 rssi=-61 dBm time=9.350 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=254 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=255 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=256 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=257 ttl=64 rssi=-61 dBm time=9.657 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=258 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=259 ttl=64 rssi=-61 dBm time=13.490 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=260 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=261 ttl=64 rssi=-61 dBm time=14.580 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=262 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=263 ttl=64 rssi=-62 dBm time=12.850 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=264 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=265 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=266 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=267 ttl=64 rssi=-61 dBm time=13.756 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=268 ttl=64 rssi=-61 dBm time=10.948 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=269 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=270 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=271 ttl=64 rssi=-61 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=272 ttl=64 rssi=-61 dBm time=10.621 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=273 ttl=64 rssi=-61 dBm time=10.766 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=275 ttl=64 rssi=-61 dBm time=11.164 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=276 ttl=64 rssi=-61 dBm time=14.911 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=277 ttl=64 rssi=-61 dBm time=10.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=278 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=278 ttl=64 rssi=-62 dBm time=21.648 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=279 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=280 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=281 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=282 ttl=64 rssi=-61 dBm time=9.344 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=283 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=284 ttl=64 rssi=-61 dBm time=11.259 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=285 ttl=64 rssi=-61 dBm time=9.349 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=286 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=287 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=288 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=289 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=290 ttl=64 rssi=-61 dBm time=9.988 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=291 ttl=64 rssi=-61 dBm time=10.946 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=292 ttl=64 rssi=-61 dBm time=14.401 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=293 ttl=64 rssi=-61 dBm time=10.620 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=294 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=295 ttl=64 rssi=-61 dBm time=9.987 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=296 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=297 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=298 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=299 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=300 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=301 ttl=64 rssi=-61 dBm time=17.451 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=302 ttl=64 rssi=-61 dBm time=11.262 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=303 ttl=64 rssi=-61 dBm time=9.988 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=304 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=305 ttl=64 rssi=-61 dBm time=10.949 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=306 ttl=64 rssi=-61 dBm time=11.259 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=307 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=308 ttl=64 rssi=-61 dBm time=9.036 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=309 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=310 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=311 ttl=64 rssi=-61 dBm time=12.037 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=312 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=313 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=314 ttl=64 rssi=-61 dBm time=12.850 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=315 ttl=64 rssi=-61 dBm time=10.309 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=316 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=317 ttl=64 rssi=-61 dBm time=10.766 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=318 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=319 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=320 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=321 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=322 ttl=64 rssi=-61 dBm time=12.024 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=324 ttl=64 rssi=-61 dBm time=14.270 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=325 ttl=64 rssi=-61 dBm time=16.493 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=326 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=326 ttl=64 rssi=-61 dBm time=20.645 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=327 ttl=64 rssi=-61 dBm time=12.210 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=328 ttl=64 rssi=-61 dBm time=10.944 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=329 ttl=64 rssi=-61 dBm time=12.209 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=330 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=331 ttl=64 rssi=-61 dBm time=10.613 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=332 ttl=64 rssi=-61 dBm time=11.570 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=333 ttl=64 rssi=-61 dBm time=11.571 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=334 ttl=64 rssi=-61 dBm time=10.944 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=335 ttl=64 rssi=-61 dBm time=10.933 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=336 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=337 ttl=64 rssi=-61 dBm time=16.174 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=338 ttl=64 rssi=-61 dBm time=17.770 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=339 ttl=64 rssi=-61 dBm time=15.355 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=340 ttl=64 rssi=-61 dBm time=12.528 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=341 ttl=64 rssi=-61 dBm time=10.613 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=342 ttl=64 rssi=-61 dBm time=16.003 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=343 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=344 ttl=64 rssi=-61 dBm time=13.167 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=345 ttl=64 rssi=-61 dBm time=13.487 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=346 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=347 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=348 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=349 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=350 ttl=64 rssi=-61 dBm time=14.258 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=351 ttl=64 rssi=-61 dBm time=13.487 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=352 ttl=64 rssi=-61 dBm time=11.265 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=353 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=354 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=355 ttl=64 rssi=-61 dBm time=10.623 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=356 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=357 ttl=64 rssi=-61 dBm time=12.850 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=358 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=359 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=360 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=361 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=362 ttl=64 rssi=-61 dBm time=9.656 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=363 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=364 ttl=64 rssi=-61 dBm time=13.489 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=365 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=366 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=367 ttl=64 rssi=-61 dBm time=13.168 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=368 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=369 ttl=64 rssi=-62 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=370 ttl=64 rssi=-61 dBm time=13.488 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=371 ttl=64 rssi=-61 dBm time=17.134 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=373 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=374 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=374 ttl=64 rssi=-61 dBm time=21.347 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=375 ttl=64 rssi=-61 dBm time=9.983 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=376 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=377 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=378 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=379 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=380 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=381 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=382 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=383 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=384 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=385 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=386 ttl=64 rssi=-61 dBm time=10.440 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=387 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=388 ttl=64 rssi=-61 dBm time=10.629 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=389 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=390 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=391 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=392 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=393 ttl=64 rssi=-61 dBm time=11.266 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=394 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=395 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=396 ttl=64 rssi=-61 dBm time=9.350 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=397 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=398 ttl=64 rssi=-61 dBm time=12.849 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=399 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=400 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=401 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=402 ttl=64 rssi=-61 dBm time=9.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=403 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=404 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=405 ttl=64 rssi=-61 dBm time=12.857 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=406 ttl=64 rssi=-61 dBm time=10.945 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=407 ttl=64 rssi=-61 dBm time=10.306 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=408 ttl=64 rssi=-61 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=409 ttl=64 rssi=-61 dBm time=9.657 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=410 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=411 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=412 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=413 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=414 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=415 ttl=64 rssi=-62 dBm time=17.269 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=416 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=417 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=418 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=419 ttl=64 rssi=-62 dBm time=23.786 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=421 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=422 ttl=64 rssi=-61 dBm time=18.091 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=423 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=423 ttl=64 rssi=-61 dBm time=20.685 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=424 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=425 ttl=64 rssi=-61 dBm time=17.133 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=425 ttl=64 rssi=-61 dBm time=26.595 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=426 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=427 ttl=64 rssi=-61 dBm time=9.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=428 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=429 ttl=64 rssi=-61 dBm time=10.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=430 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=431 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=432 ttl=64 rssi=-61 dBm time=11.264 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=433 ttl=64 rssi=-61 dBm time=11.265 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=434 ttl=64 rssi=-61 dBm time=13.491 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=435 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=436 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=437 ttl=64 rssi=-61 dBm time=21.426 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=438 ttl=64 rssi=-61 dBm time=11.902 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=439 ttl=64 rssi=-61 dBm time=10.943 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=440 ttl=64 rssi=-61 dBm time=10.614 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=441 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=442 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=443 ttl=64 rssi=-61 dBm time=9.985 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=444 ttl=64 rssi=-61 dBm time=12.345 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=445 ttl=64 rssi=-61 dBm time=11.266 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=446 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=447 ttl=64 rssi=-61 dBm time=10.308 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=448 ttl=64 rssi=-61 dBm time=10.617 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=449 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=450 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=451 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=452 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=453 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=454 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=455 ttl=64 rssi=-61 dBm time=11.581 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=456 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=457 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=458 ttl=64 rssi=-61 dBm time=13.171 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=459 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=460 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=461 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=462 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=463 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=464 ttl=64 rssi=-62 dBm time=14.273 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=465 ttl=64 rssi=-62 dBm time=18.868 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=466 ttl=64 rssi=-61 dBm time=22.389 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=467 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=468 ttl=64 rssi=-61 dBm time=15.175 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=469 ttl=64 rssi=-61 dBm time=12.027 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=470 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=471 ttl=64 rssi=-61 dBm time=9.658 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=472 ttl=64 rssi=-61 dBm time=10.625 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=473 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=474 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=475 ttl=64 rssi=-61 dBm time=14.582 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=476 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=477 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=478 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=479 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=480 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=481 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=482 ttl=64 rssi=-61 dBm time=13.172 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=483 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=484 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=485 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=486 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=487 ttl=64 rssi=-61 dBm time=14.901 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=488 ttl=64 rssi=-61 dBm time=9.344 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=489 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=490 ttl=64 rssi=-61 dBm time=9.978 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=491 ttl=64 rssi=-61 dBm time=13.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=492 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=493 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=494 ttl=64 rssi=-61 dBm time=10.617 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=495 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=496 ttl=64 rssi=-61 dBm time=13.171 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=497 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=498 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=499 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=500 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=501 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=502 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=503 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=504 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=505 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=506 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=507 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=508 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=509 ttl=64 rssi=-61 dBm time=9.983 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=510 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=511 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=512 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=513 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=514 ttl=64 rssi=-62 dBm time=14.262 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=518 ttl=64 rssi=-61 dBm time=15.539 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=519 ttl=64 rssi=-61 dBm time=13.171 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=519 ttl=64 rssi=-61 dBm time=22.602 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=520 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=521 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=522 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=523 ttl=64 rssi=-61 dBm time=9.978 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=524 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=525 ttl=64 rssi=-61 dBm time=10.947 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=526 ttl=64 rssi=-62 dBm time=10.628 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=527 ttl=64 rssi=-61 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=528 ttl=64 rssi=-61 dBm time=12.214 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=529 ttl=64 rssi=-61 dBm time=11.267 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=530 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=531 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=532 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=533 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=534 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=535 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=536 ttl=64 rssi=-61 dBm time=11.576 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=537 ttl=64 rssi=-61 dBm time=14.900 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=538 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=539 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=540 ttl=64 rssi=-61 dBm time=20.460 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=541 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=542 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=543 ttl=64 rssi=-61 dBm time=15.674 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=544 ttl=64 rssi=-62 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=545 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=546 ttl=64 rssi=-61 dBm time=10.617 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=547 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=548 ttl=64 rssi=-61 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=549 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=550 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=551 ttl=64 rssi=-61 dBm time=10.940 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=552 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=553 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=554 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=555 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=556 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=557 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=558 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=559 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=560 ttl=64 rssi=-61 dBm time=12.538 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=561 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=562 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=563 ttl=64 rssi=-61 dBm time=19.833 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=565 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=565 ttl=64 rssi=-61 dBm time=20.655 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=566 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=566 ttl=64 rssi=-61 dBm time=21.322 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=567 ttl=64 rssi=-61 dBm time=9.982 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=568 ttl=64 rssi=-61 dBm time=9.657 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=569 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=570 ttl=64 rssi=-61 dBm time=10.626 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=571 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=572 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=573 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=574 ttl=64 rssi=-61 dBm time=12.530 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=575 ttl=64 rssi=-61 dBm time=15.856 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=576 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=577 ttl=64 rssi=-60 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=578 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=579 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=580 ttl=64 rssi=-61 dBm time=10.940 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=581 ttl=64 rssi=-61 dBm time=10.940 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=582 ttl=64 rssi=-61 dBm time=10.302 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=583 ttl=64 rssi=-61 dBm time=9.350 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=584 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=585 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=586 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=587 ttl=64 rssi=-61 dBm time=12.672 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=588 ttl=64 rssi=-61 dBm time=11.839 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=589 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=590 ttl=64 rssi=-61 dBm time=14.582 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=591 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=592 ttl=64 rssi=-61 dBm time=13.489 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=593 ttl=64 rssi=-61 dBm time=16.496 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=594 ttl=64 rssi=-61 dBm time=11.252 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=595 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=596 ttl=64 rssi=-61 dBm time=9.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=597 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=598 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=599 ttl=64 rssi=-61 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=600 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=601 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=602 ttl=64 rssi=-61 dBm time=14.898 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=603 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=604 ttl=64 rssi=-62 dBm time=12.529 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=605 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=606 ttl=64 rssi=-61 dBm time=10.940 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=607 ttl=64 rssi=-61 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=608 ttl=64 rssi=-61 dBm time=10.295 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=609 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=610 ttl=64 rssi=-61 dBm time=13.315 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=611 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=612 ttl=64 rssi=-61 dBm time=23.335 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=613 ttl=64 rssi=-61 dBm time=10.628 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=614 ttl=64 rssi=-61 dBm time=12.666 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=615 ttl=64 rssi=-61 dBm time=10.303 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=615 ttl=64 rssi=-61 dBm time=19.692 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=616 ttl=64 rssi=-61 dBm time=12.850 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=616 ttl=64 rssi=-61 dBm time=22.306 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=617 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=618 ttl=64 rssi=-61 dBm time=17.906 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=618 ttl=64 rssi=-61 dBm time=27.361 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=619 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=620 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=621 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=622 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=623 ttl=64 rssi=-61 dBm time=13.489 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=624 ttl=64 rssi=-61 dBm time=13.489 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=625 ttl=64 rssi=-61 dBm time=14.591 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=626 ttl=64 rssi=-61 dBm time=12.857 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=628 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=629 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=630 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=631 ttl=64 rssi=-61 dBm time=12.214 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=632 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=633 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=634 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=635 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=636 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=637 ttl=64 rssi=-61 dBm time=14.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=638 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=639 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=640 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=641 ttl=64 rssi=-62 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=642 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=643 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=644 ttl=64 rssi=-61 dBm time=12.346 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=645 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=646 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=647 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=648 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=649 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=650 ttl=64 rssi=-61 dBm time=9.658 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=651 ttl=64 rssi=-61 dBm time=16.630 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=652 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=653 ttl=64 rssi=-61 dBm time=9.982 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=654 ttl=64 rssi=-61 dBm time=9.035 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=655 ttl=64 rssi=-61 dBm time=9.658 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=656 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=657 ttl=64 rssi=-61 dBm time=13.169 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=658 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=659 ttl=64 rssi=-61 dBm time=11.388 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=662 ttl=64 rssi=-61 dBm time=21.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=663 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=663 ttl=64 rssi=-61 dBm time=20.998 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=664 ttl=64 rssi=-61 dBm time=9.658 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=665 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=666 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=667 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=668 ttl=64 rssi=-61 dBm time=12.991 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=669 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=670 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=671 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=672 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=673 ttl=64 rssi=-61 dBm time=9.988 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=674 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=675 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=676 ttl=64 rssi=-61 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=677 ttl=64 rssi=-62 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=678 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=679 ttl=64 rssi=-61 dBm time=11.896 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=680 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=681 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=682 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=683 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=684 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=685 ttl=64 rssi=-61 dBm time=11.895 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=686 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=687 ttl=64 rssi=-61 dBm time=10.943 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=688 ttl=64 rssi=-61 dBm time=11.576 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=689 ttl=64 rssi=-61 dBm time=11.256 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=690 ttl=64 rssi=-61 dBm time=13.626 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=691 ttl=64 rssi=-61 dBm time=11.525 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=692 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=693 ttl=64 rssi=-61 dBm time=11.407 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=694 ttl=64 rssi=-61 dBm time=12.346 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=695 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=696 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=697 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=698 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=699 ttl=64 rssi=-61 dBm time=9.979 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=700 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=701 ttl=64 rssi=-61 dBm time=11.576 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=702 ttl=64 rssi=-62 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=703 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=704 ttl=64 rssi=-61 dBm time=10.942 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=705 ttl=64 rssi=-61 dBm time=10.303 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=706 ttl=64 rssi=-61 dBm time=10.623 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=707 ttl=64 rssi=-61 dBm time=9.664 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=710 ttl=64 rssi=-61 dBm time=9.664 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=710 ttl=64 rssi=-61 dBm time=19.020 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=711 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=711 ttl=64 rssi=-61 dBm time=21.381 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=712 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=713 ttl=64 rssi=-62 dBm time=9.036 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=714 ttl=64 rssi=-61 dBm time=11.262 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=715 ttl=64 rssi=-61 dBm time=15.998 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=716 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=717 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=718 ttl=64 rssi=-61 dBm time=10.296 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=719 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=720 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=721 ttl=64 rssi=-61 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=722 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=723 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=724 ttl=64 rssi=-61 dBm time=9.982 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=725 ttl=64 rssi=-61 dBm time=10.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=726 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=727 ttl=64 rssi=-61 dBm time=11.263 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=728 ttl=64 rssi=-61 dBm time=12.850 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=729 ttl=64 rssi=-61 dBm time=12.211 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=730 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=731 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=732 ttl=64 rssi=-61 dBm time=11.891 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=733 ttl=64 rssi=-61 dBm time=11.572 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=734 ttl=64 rssi=-61 dBm time=10.615 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=735 ttl=64 rssi=-61 dBm time=9.658 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=736 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=737 ttl=64 rssi=-61 dBm time=19.184 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=738 ttl=64 rssi=-61 dBm time=13.952 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=739 ttl=64 rssi=-62 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=740 ttl=64 rssi=-61 dBm time=11.707 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=741 ttl=64 rssi=-61 dBm time=14.272 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=742 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=743 ttl=64 rssi=-61 dBm time=19.506 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=744 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=745 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=746 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=747 ttl=64 rssi=-61 dBm time=10.303 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=748 ttl=64 rssi=-61 dBm time=10.621 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=749 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=750 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=751 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=752 ttl=64 rssi=-61 dBm time=9.037 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=753 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=754 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=755 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=756 ttl=64 rssi=-61 dBm time=20.601 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=758 ttl=64 rssi=-61 dBm time=12.618 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=759 ttl=64 rssi=-61 dBm time=9.670 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=759 ttl=64 rssi=-61 dBm time=19.011 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=760 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=760 ttl=64 rssi=-61 dBm time=21.351 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=761 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=762 ttl=64 rssi=-61 dBm time=13.942 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=763 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=764 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=765 ttl=64 rssi=-61 dBm time=14.590 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=766 ttl=64 rssi=-62 dBm time=10.941 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=767 ttl=64 rssi=-61 dBm time=9.672 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=768 ttl=64 rssi=-61 dBm time=13.303 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=769 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=770 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=771 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=772 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=773 ttl=64 rssi=-61 dBm time=10.309 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=774 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=775 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=776 ttl=64 rssi=-61 dBm time=11.895 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=777 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=778 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=779 ttl=64 rssi=-61 dBm time=10.628 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=780 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=781 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=782 ttl=64 rssi=-61 dBm time=12.853 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=783 ttl=64 rssi=-61 dBm time=9.990 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=784 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=785 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=786 ttl=64 rssi=-61 dBm time=10.299 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=787 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=788 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=789 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=790 ttl=64 rssi=-61 dBm time=15.539 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=791 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=792 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=793 ttl=64 rssi=-61 dBm time=15.539 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=794 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=795 ttl=64 rssi=-62 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=796 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=797 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=798 ttl=64 rssi=-61 dBm time=13.172 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=799 ttl=64 rssi=-61 dBm time=11.267 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=800 ttl=64 rssi=-61 dBm time=16.188 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=801 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=802 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=803 ttl=64 rssi=-61 dBm time=10.934 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=804 ttl=64 rssi=-61 dBm time=13.171 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=806 ttl=64 rssi=-61 dBm time=13.954 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=807 ttl=64 rssi=-61 dBm time=14.900 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=808 ttl=64 rssi=-61 dBm time=9.665 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=809 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=810 ttl=64 rssi=-61 dBm time=10.298 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=811 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=812 ttl=64 rssi=-61 dBm time=13.624 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=813 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=814 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=815 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=816 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=817 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=818 ttl=64 rssi=-61 dBm time=9.978 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=819 ttl=64 rssi=-61 dBm time=9.976 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=820 ttl=64 rssi=-62 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=821 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=822 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=823 ttl=64 rssi=-61 dBm time=13.489 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=824 ttl=64 rssi=-61 dBm time=11.266 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=825 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=826 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=827 ttl=64 rssi=-61 dBm time=13.943 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=828 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=829 ttl=64 rssi=-61 dBm time=10.617 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=830 ttl=64 rssi=-61 dBm time=13.173 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=831 ttl=64 rssi=-61 dBm time=13.170 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=832 ttl=64 rssi=-61 dBm time=11.256 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=833 ttl=64 rssi=-61 dBm time=9.659 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=834 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=835 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=836 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=837 ttl=64 rssi=-61 dBm time=14.083 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=838 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=839 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=840 ttl=64 rssi=-61 dBm time=16.179 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=841 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=842 ttl=64 rssi=-61 dBm time=13.491 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=843 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=844 ttl=64 rssi=-61 dBm time=13.317 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=845 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=846 ttl=64 rssi=-61 dBm time=13.172 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=847 ttl=64 rssi=-61 dBm time=10.309 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=848 ttl=64 rssi=-61 dBm time=9.663 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=849 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=850 ttl=64 rssi=-61 dBm time=11.900 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=851 ttl=64 rssi=-61 dBm time=10.635 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=852 ttl=64 rssi=-62 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=854 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=855 ttl=64 rssi=-61 dBm time=16.497 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=856 ttl=64 rssi=-61 dBm time=13.173 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=856 ttl=64 rssi=-61 dBm time=22.661 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=857 ttl=64 rssi=-61 dBm time=10.628 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=858 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=859 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=860 ttl=64 rssi=-61 dBm time=9.977 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=861 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=862 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=863 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=864 ttl=64 rssi=-61 dBm time=11.260 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=865 ttl=64 rssi=-61 dBm time=11.573 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=866 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=867 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=868 ttl=64 rssi=-61 dBm time=13.304 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=869 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=870 ttl=64 rssi=-61 dBm time=11.892 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=871 ttl=64 rssi=-61 dBm time=10.626 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=872 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=873 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=874 ttl=64 rssi=-61 dBm time=10.617 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=875 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=876 ttl=64 rssi=-61 dBm time=12.214 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=877 ttl=64 rssi=-61 dBm time=9.989 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=878 ttl=64 rssi=-61 dBm time=11.266 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=879 ttl=64 rssi=-62 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=880 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=881 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=882 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=883 ttl=64 rssi=-61 dBm time=10.298 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=884 ttl=64 rssi=-61 dBm time=13.173 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=885 ttl=64 rssi=-61 dBm time=11.256 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=886 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=887 ttl=64 rssi=-61 dBm time=13.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=888 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=889 ttl=64 rssi=-61 dBm time=9.659 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=890 ttl=64 rssi=-61 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=891 ttl=64 rssi=-61 dBm time=12.214 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=892 ttl=64 rssi=-61 dBm time=12.853 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=893 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=894 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=895 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=896 ttl=64 rssi=-61 dBm time=11.256 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=897 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=898 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=899 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=902 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=903 ttl=64 rssi=-61 dBm time=15.221 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=904 ttl=64 rssi=-61 dBm time=10.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=904 ttl=64 rssi=-61 dBm time=20.092 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=905 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=906 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=907 ttl=64 rssi=-61 dBm time=12.533 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=908 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=909 ttl=64 rssi=-61 dBm time=13.171 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=910 ttl=64 rssi=-61 dBm time=11.576 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=911 ttl=64 rssi=-61 dBm time=9.344 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=912 ttl=64 rssi=-61 dBm time=9.350 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=913 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=914 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=915 ttl=64 rssi=-61 dBm time=9.345 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=916 ttl=64 rssi=-61 dBm time=11.261 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=917 ttl=64 rssi=-61 dBm time=10.935 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=918 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=919 ttl=64 rssi=-61 dBm time=12.213 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=920 ttl=64 rssi=-61 dBm time=12.531 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=921 ttl=64 rssi=-61 dBm time=11.253 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=922 ttl=64 rssi=-61 dBm time=9.668 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=923 ttl=64 rssi=-61 dBm time=11.254 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=924 ttl=64 rssi=-61 dBm time=11.574 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=925 ttl=64 rssi=-61 dBm time=10.307 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=926 ttl=64 rssi=-61 dBm time=9.659 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=927 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=928 ttl=64 rssi=-61 dBm time=12.853 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=929 ttl=64 rssi=-61 dBm time=10.627 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=930 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=931 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=932 ttl=64 rssi=-61 dBm time=10.943 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=933 ttl=64 rssi=-61 dBm time=9.037 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=934 ttl=64 rssi=-61 dBm time=10.299 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=935 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=936 ttl=64 rssi=-61 dBm time=11.895 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=937 ttl=64 rssi=-61 dBm time=12.851 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=938 ttl=64 rssi=-61 dBm time=12.212 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=939 ttl=64 rssi=-61 dBm time=10.308 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=940 ttl=64 rssi=-61 dBm time=9.659 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=941 ttl=64 rssi=-61 dBm time=9.670 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=942 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=943 ttl=64 rssi=-61 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=944 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=945 ttl=64 rssi=-61 dBm time=10.947 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=946 ttl=64 rssi=-61 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=947 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=948 ttl=64 rssi=-61 dBm time=15.543 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=950 ttl=64 rssi=-61 dBm time=11.266 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=951 ttl=64 rssi=-61 dBm time=16.177 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=952 ttl=64 rssi=-61 dBm time=11.255 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=952 ttl=64 rssi=-61 dBm time=20.716 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=953 ttl=64 rssi=-61 dBm time=13.172 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=953 ttl=64 rssi=-61 dBm time=22.608 ms (DUP!)
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=954 ttl=64 rssi=-61 dBm time=12.852 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=955 ttl=64 rssi=-61 dBm time=12.532 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=956 ttl=64 rssi=-61 dBm time=10.948 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=957 ttl=64 rssi=-61 dBm time=11.896 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=958 ttl=64 rssi=-61 dBm time=10.299 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=959 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=960 ttl=64 rssi=-61 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=961 ttl=64 rssi=-61 dBm time=11.256 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=962 ttl=64 rssi=-61 dBm time=9.984 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=963 ttl=64 rssi=-61 dBm time=10.623 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=964 ttl=64 rssi=-61 dBm time=10.623 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=965 ttl=64 rssi=-61 dBm time=9.978 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=966 ttl=64 rssi=-61 dBm time=10.299 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=967 ttl=64 rssi=-61 dBm time=10.309 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=968 ttl=64 rssi=-61 dBm time=11.262 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=969 ttl=64 rssi=-61 dBm time=10.303 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=970 ttl=64 rssi=-61 dBm time=11.256 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=971 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=972 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=973 ttl=64 rssi=-61 dBm time=10.942 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=974 ttl=64 rssi=-61 dBm time=11.257 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=975 ttl=64 rssi=-61 dBm time=11.894 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=976 ttl=64 rssi=-61 dBm time=10.937 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=977 ttl=64 rssi=-61 dBm time=10.616 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=978 ttl=64 rssi=-61 dBm time=11.893 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=979 ttl=64 rssi=-61 dBm time=10.297 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=980 ttl=64 rssi=-61 dBm time=9.670 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=981 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=982 ttl=64 rssi=-61 dBm time=10.936 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=983 ttl=64 rssi=-61 dBm time=10.628 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=984 ttl=64 rssi=-61 dBm time=10.298 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=985 ttl=64 rssi=-61 dBm time=10.309 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=986 ttl=64 rssi=-61 dBm time=9.346 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=987 ttl=64 rssi=-61 dBm time=11.576 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=988 ttl=64 rssi=-61 dBm time=11.575 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=989 ttl=64 rssi=-61 dBm time=11.895 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=990 ttl=64 rssi=-61 dBm time=10.308 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=991 ttl=64 rssi=-61 dBm time=10.622 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=992 ttl=64 rssi=-61 dBm time=9.984 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=993 ttl=64 rssi=-61 dBm time=9.346 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=994 ttl=64 rssi=-61 dBm time=9.660 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=995 ttl=64 rssi=-61 dBm time=10.298 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=996 ttl=64 rssi=-61 dBm time=13.626 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=998 ttl=64 rssi=-61 dBm time=12.984 ms
58 bytes from fe80::a405:7be5:c51e:1192%6: icmp_seq=999 ttl=64 rssi=-61 dBm time=17.775 ms

--- ff02::1 PING statistics ---
1000 packets transmitted, 974 packets received, 27 duplicates, 2% packet loss
round-trip min/avg/max = 9.034/12.044/27.361 ms
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 384
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 592
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> 
```
