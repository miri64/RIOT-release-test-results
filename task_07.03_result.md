# 07. Task 03 - ICMPv6 echo on iotlab-m3 with three hops (RPL route) [PASSED]
## Captured stdout setup

```
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271562 --list saclay,m3,1 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271562 --list saclay,m3,2 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271562 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271562 --list saclay,m3,12 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
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
          
           White-listed link layer addresses:
            --- none ---

          Statistics for Layer 2
            RX packets 9  bytes 387
            TX packets 5 (Multicast: 5)  bytes 215
            TX succeeded 5 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
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
          
           White-listed link layer addresses:
            --- none ---

          Statistics for Layer 2
            RX packets 7  bytes 301
            TX packets 4 (Multicast: 4)  bytes 172
            TX succeeded 4 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
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
          
           White-listed link layer addresses:
            --- none ---

          Statistics for Layer 2
            RX packets 4  bytes 172
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
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
          
           White-listed link layer addresses:
            --- none ---

          Statistics for Layer 2
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 86
            TX succeeded 2 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 128
            TX succeeded 2 errors 0

> ifconfig 5 l2filter add EE:19:4D:E3:D3:BA:17:32
ifconfig 5 l2filter add EE:19:4D:E3:D3:BA:17:32
successfully added address to filter
> ifconfig 5 l2filter add A6:51:FA:B5:22:0D:A6:85
ifconfig 5 l2filter add A6:51:FA:B5:22:0D:A6:85
successfully added address to filter
> ifconfig 5 l2filter add A6:05:7B:E5:C5:1E:11:92
ifconfig 5 l2filter add A6:05:7B:E5:C5:1E:11:92
successfully added address to filter
> ifconfig 5 l2filter add E6:2E:CE:92:CA:67:B6:2B
ifconfig 5 l2filter add E6:2E:CE:92:CA:67:B6:2B
successfully added address to filter
> ifconfig 5 l2filter add EE:19:4D:E3:D3:BA:17:32
ifconfig 5 l2filter add EE:19:4D:E3:D3:BA:17:32
successfully added address to filter
> ifconfig 5 l2filter add A6:51:FA:B5:22:0D:A6:85
ifconfig 5 l2filter add A6:51:FA:B5:22:0D:A6:85
successfully added address to filter
> ifconfig 5 add 2001:db8::a405:7be5:c51e:1192/64
ifconfig 5 add 2001:db8::a405:7be5:c51e:1192/64
success: added 2001:db8::a405:7be5:c51e:1192/64 to interface 5
> rpl init 5
rpl init 5
successfully initialized RPL on interface 5
> rpl root 0 2001:db8::a405:7be5:c51e:1192
rpl root 0 2001:db8::a405:7be5:c51e:1192
successfully added a new RPL DODAG
> rpl init 5
rpl init 5
successfully initialized RPL on interface 5
> rpl init 5
rpl init 5
successfully initialized RPL on interface 5
> rpl init 5
rpl init 5
successfully initialized RPL on interface 5
> rpl show
rpl show
instance table:	[X]	
parent table:	[X]	[ ]	[ ]	

instance [0 | Iface: 5 | mop: 2 | ocp: 0 | mhri: 256 | mri 0]
	dodag [2001:db8::a405:7be5:c51e:1192 | R: 512 | OP: Router | PIO: on | TR(I=[8,20], k=10, c=0)]
		parent [addr: fe80::a405:7be5:c51e:1192 | rank: 256]
> rpl show
rpl show
instance table:	[X]	
parent table:	[X]	[ ]	[ ]	

instance [0 | Iface: 5 | mop: 2 | ocp: 0 | mhri: 256 | mri 0]
	dodag [2001:db8::a405:7be5:c51e:1192 | R: 768 | OP: Router | PIO: on | TR(I=[8,20], k=10, c=2)]
		parent [addr: fe80::ec19:4de3:d3ba:1732 | rank: 512]
> rpl show
rpl show
instance table:	[X]	
parent table:	[X]	[ ]	[ ]	

instance [0 | Iface: 5 | mop: 2 | ocp: 0 | mhri: 256 | mri 0]
	dodag [2001:db8::a405:7be5:c51e:1192 | R: 1024 | OP: Router | PIO: on | TR(I=[8,20], k=10, c=0)]
		parent [addr: fe80::a451:fab5:220d:a685 | rank: 768]
> 
```

## Captured stdout call

```
ifconfig
ifconfig
Iface  5  HWaddr: 11:92  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: A6:05:7B:E5:C5:1E:11:92 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::a405:7be5:c51e:1192  scope: link  VAL
          inet6 addr: 2001:db8::a405:7be5:c51e:1192  scope: global  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff1e:1192
          inet6 group: ff02::1a
          
           White-listed link layer addresses:
             0: EE:19:4D:E3:D3:BA:17:32

          Statistics for Layer 2
            RX packets 47  bytes 3140
            TX packets 21 (Multicast: 18)  bytes 1336
            TX succeeded 21 errors 0
          Statistics for IPv6
            RX packets 14  bytes 1276
            TX packets 21 (Multicast: 18)  bytes 1762
            TX succeeded 21 errors 0

> ping6 2001:db8::a405:7be5:c51e:1192 -c 100 -i 100 -s 50 -W 1000
ping6 2001:db8::a405:7be5:c51e:1192 -c 100 -i 100 -s 50 -W 1000
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=0 ttl=62 rssi=-42 dBm time=39.790 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=1 ttl=62 rssi=-41 dBm time=41.717 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=2 ttl=62 rssi=-42 dBm time=37.554 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=3 ttl=62 rssi=-41 dBm time=41.395 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=4 ttl=62 rssi=-41 dBm time=44.922 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=5 ttl=62 rssi=-42 dBm time=44.580 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=6 ttl=62 rssi=-42 dBm time=43.949 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=7 ttl=62 rssi=-42 dBm time=43.318 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=8 ttl=62 rssi=-42 dBm time=40.438 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=9 ttl=62 rssi=-42 dBm time=41.395 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=10 ttl=62 rssi=-42 dBm time=41.710 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=11 ttl=62 rssi=-42 dBm time=40.122 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=12 ttl=62 rssi=-41 dBm time=42.030 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=13 ttl=62 rssi=-41 dBm time=46.509 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=14 ttl=62 rssi=-43 dBm time=41.075 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=15 ttl=62 rssi=-41 dBm time=38.829 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=16 ttl=62 rssi=-42 dBm time=41.709 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=17 ttl=62 rssi=-43 dBm time=43.309 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=18 ttl=62 rssi=-42 dBm time=40.435 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=19 ttl=62 rssi=-42 dBm time=43.629 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=20 ttl=62 rssi=-41 dBm time=39.161 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=21 ttl=62 rssi=-42 dBm time=41.388 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=22 ttl=62 rssi=-43 dBm time=44.000 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=23 ttl=62 rssi=-42 dBm time=42.036 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=24 ttl=62 rssi=-42 dBm time=41.403 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=25 ttl=62 rssi=-42 dBm time=46.002 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=26 ttl=62 rssi=-43 dBm time=37.876 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=27 ttl=62 rssi=-43 dBm time=41.709 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=28 ttl=62 rssi=-42 dBm time=41.075 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=29 ttl=62 rssi=-42 dBm time=39.162 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=30 ttl=62 rssi=-43 dBm time=40.115 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=31 ttl=62 rssi=-41 dBm time=44.286 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=32 ttl=62 rssi=-41 dBm time=44.269 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=33 ttl=62 rssi=-43 dBm time=43.949 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=34 ttl=62 rssi=-43 dBm time=38.207 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=35 ttl=62 rssi=-43 dBm time=42.988 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=36 ttl=62 rssi=-41 dBm time=43.316 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=37 ttl=62 rssi=-42 dBm time=38.835 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=38 ttl=62 rssi=-41 dBm time=42.688 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=39 ttl=62 rssi=-42 dBm time=39.475 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=40 ttl=62 rssi=-42 dBm time=44.595 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=41 ttl=62 rssi=-42 dBm time=41.715 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=42 ttl=62 rssi=-42 dBm time=43.629 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=43 ttl=62 rssi=-43 dBm time=43.317 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=44 ttl=62 rssi=-43 dBm time=43.638 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=45 ttl=62 rssi=-41 dBm time=42.662 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=46 ttl=62 rssi=-42 dBm time=42.995 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=47 ttl=62 rssi=-42 dBm time=41.069 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=48 ttl=62 rssi=-41 dBm time=38.529 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=49 ttl=62 rssi=-40 dBm time=42.669 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=50 ttl=62 rssi=-41 dBm time=40.441 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=51 ttl=62 rssi=-42 dBm time=37.241 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=52 ttl=62 rssi=-42 dBm time=41.069 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=53 ttl=62 rssi=-42 dBm time=42.669 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=54 ttl=62 rssi=-43 dBm time=42.356 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=55 ttl=62 rssi=-42 dBm time=42.356 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=56 ttl=62 rssi=-42 dBm time=41.398 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=57 ttl=62 rssi=-42 dBm time=41.710 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=58 ttl=62 rssi=-42 dBm time=42.670 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=59 ttl=62 rssi=-42 dBm time=44.270 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=60 ttl=62 rssi=-41 dBm time=45.230 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=61 ttl=62 rssi=-41 dBm time=44.269 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=62 ttl=62 rssi=-43 dBm time=41.395 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=63 ttl=62 rssi=-42 dBm time=41.077 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=64 ttl=62 rssi=-42 dBm time=39.469 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=65 ttl=62 rssi=-43 dBm time=39.475 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=66 ttl=62 rssi=-43 dBm time=41.090 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=67 ttl=62 rssi=-43 dBm time=39.169 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=68 ttl=62 rssi=-42 dBm time=46.775 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=69 ttl=62 rssi=-43 dBm time=42.669 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=70 ttl=62 rssi=-41 dBm time=42.029 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=71 ttl=62 rssi=-42 dBm time=37.887 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=72 ttl=62 rssi=-41 dBm time=36.287 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=73 ttl=62 rssi=-42 dBm time=42.029 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=74 ttl=62 rssi=-42 dBm time=42.349 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=75 ttl=62 rssi=-42 dBm time=40.755 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=76 ttl=62 rssi=-42 dBm time=40.429 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=77 ttl=62 rssi=-41 dBm time=44.270 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=78 ttl=62 rssi=-41 dBm time=43.629 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=79 ttl=62 rssi=-41 dBm time=37.870 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=80 ttl=62 rssi=-41 dBm time=43.309 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=81 ttl=62 rssi=-41 dBm time=42.989 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=82 ttl=62 rssi=-43 dBm time=41.389 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=83 ttl=62 rssi=-41 dBm time=43.963 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=84 ttl=62 rssi=-41 dBm time=46.829 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=85 ttl=62 rssi=-42 dBm time=42.998 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=86 ttl=62 rssi=-41 dBm time=39.469 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=87 ttl=62 rssi=-42 dBm time=44.269 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=88 ttl=62 rssi=-42 dBm time=42.355 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=89 ttl=62 rssi=-42 dBm time=39.481 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=90 ttl=62 rssi=-42 dBm time=43.629 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=91 ttl=62 rssi=-43 dBm time=41.721 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=92 ttl=62 rssi=-42 dBm time=40.761 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=93 ttl=62 rssi=-43 dBm time=41.389 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=94 ttl=62 rssi=-42 dBm time=41.389 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=95 ttl=62 rssi=-41 dBm time=44.589 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=96 ttl=62 rssi=-41 dBm time=41.075 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=97 ttl=62 rssi=-42 dBm time=40.755 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=98 ttl=62 rssi=-42 dBm time=42.675 ms
58 bytes from 2001:db8::a405:7be5:c51e:1192: icmp_seq=99 ttl=62 rssi=-41 dBm time=39.807 ms

--- 2001:db8::a405:7be5:c51e:1192 PING statistics ---
100 packets transmitted, 100 packets received, 0% packet loss
round-trip min/avg/max = 36.287/41.843/46.829 ms
> pktbuf
pktbuf
packet buffer: first byte: 0x20001ebc, last byte: 0x20003ebc (size: 8192)
  position of last byte used: 504
~ unused: 0x20001ebc (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001ebc, last byte: 0x20003ebc (size: 8192)
  position of last byte used: 512
~ unused: 0x20001ebc (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001ebc, last byte: 0x20003ebc (size: 8192)
  position of last byte used: 504
~ unused: 0x20001ebc (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001ebc, last byte: 0x20003ebc (size: 8192)
  position of last byte used: 472
~ unused: 0x20001ebc (next: (nil), size: 8192) ~
> 
```

