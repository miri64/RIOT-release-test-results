# 07. Task 04 - UDP on iotlab-m3 with three hops (RPL route) [PASSED]
## Captured stdout setup

```
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271563 --list saclay,m3,4 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271563 --list saclay,m3,5 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271563 --list saclay,m3,10 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin

```

## Captured stderr setup

```
HTTP Error 502: 
	<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
	<html><head>
	<title>502 Bad Gateway</title>
	</head><body>
	<h1>Bad Gateway</h1>
	<p>The proxy server received an invalid
	response from an upstream server.<br />
	</p>
	</body></html>

make: *** [/home/mlenders/Repositories/RIOT-OS/RIOT/Makefile.include:776: flash] Error 1

```

## Captured stdout setup

```
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271564 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271564 --list saclay,m3,10 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271564 --list saclay,m3,11 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  89604	    184	  21196	 110984	  1b188	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271564 --list saclay,m3,12 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-9.saclay.iot-lab.info:20000' 


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
            RX packets 9  bytes 387
            TX packets 5 (Multicast: 5)  bytes 215
            TX succeeded 5 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 5 (Multicast: 5)  bytes 320
            TX succeeded 5 errors 0

> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-10.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 67:C3  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: 7A:94:05:FF:25:8D:E7:C3 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::7894:5ff:258d:e7c3  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff8d:e7c3
          
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

> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-11.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 0B:BE  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: E6:D3:6F:EC:DF:36:0B:BE 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::e4d3:6fec:df36:bbe  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff36:bbe
          
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

> ifconfig 5 l2filter add 7A:94:05:FF:25:8D:E7:C3
ifconfig 5 l2filter add 7A:94:05:FF:25:8D:E7:C3
successfully added address to filter
> ifconfig 5 l2filter add E6:D3:6F:EC:DF:36:0B:BE
ifconfig 5 l2filter add E6:D3:6F:EC:DF:36:0B:BE
successfully added address to filter
> ifconfig 5 l2filter add A6:51:FA:B5:22:0D:A6:85
ifconfig 5 l2filter add A6:51:FA:B5:22:0D:A6:85
successfully added address to filter
> ifconfig 5 l2filter add E6:2E:CE:92:CA:67:B6:2B
ifconfig 5 l2filter add E6:2E:CE:92:CA:67:B6:2B
successfully added address to filter
> ifconfig 5 l2filter add 7A:94:05:FF:25:8D:E7:C3
ifconfig 5 l2filter add 7A:94:05:FF:25:8D:E7:C3
successfully added address to filter
> ifconfig 5 l2filter add E6:D3:6F:EC:DF:36:0B:BE
ifconfig 5 l2filter add E6:D3:6F:EC:DF:36:0B:BE
successfully added address to filter
> ifconfig 5 add 2001:db8::a451:fab5:220d:a685/64
ifconfig 5 add 2001:db8::a451:fab5:220d:a685/64
success: added 2001:db8::a451:fab5:220d:a685/64 to interface 5
> rpl init 5
rpl init 5
successfully initialized RPL on interface 5
> rpl root 0 2001:db8::a451:fab5:220d:a685
rpl root 0 2001:db8::a451:fab5:220d:a685
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
	dodag [2001:db8::a451:fab5:220d:a685 | R: 512 | OP: Router | PIO: on | TR(I=[8,20], k=10, c=0)]
		parent [addr: fe80::a451:fab5:220d:a685 | rank: 256]
> rpl show
rpl show
instance table:	[X]	
parent table:	[X]	[ ]	[ ]	

instance [0 | Iface: 5 | mop: 2 | ocp: 0 | mhri: 256 | mri 0]
	dodag [2001:db8::a451:fab5:220d:a685 | R: 768 | OP: Router | PIO: on | TR(I=[8,20], k=10, c=2)]
		parent [addr: fe80::7894:5ff:258d:e7c3 | rank: 512]
> rpl show
rpl show
instance table:	[X]	
parent table:	[X]	[ ]	[ ]	

instance [0 | Iface: 5 | mop: 2 | ocp: 0 | mhri: 256 | mri 0]
	dodag [2001:db8::a451:fab5:220d:a685 | R: 1024 | OP: Router | PIO: on | TR(I=[8,20], k=10, c=0)]
		parent [addr: fe80::e4d3:6fec:df36:bbe | rank: 768]
> 
```

## Captured stdout call

```
udp server start 1337
udp server start 1337
Success: started UDP server on port 1337
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
          inet6 addr: 2001:db8::e42e:ce92:ca67:b62b  scope: global  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff67:b62b
          inet6 group: ff02::1a
          
           White-listed link layer addresses:
             0: E6:D3:6F:EC:DF:36:0B:BE

          Statistics for Layer 2
            RX packets 39  bytes 2845
            TX packets 15 (Multicast: 13)  bytes 983
            TX succeeded 15 errors 0
          Statistics for IPv6
            RX packets 15  bytes 1394
            TX packets 15 (Multicast: 13)  bytes 1288
            TX succeeded 15 errors 0

> udp send 2001:db8::e42e:ce92:ca67:b62b 1337 50 100 100000
udp send 2001:db8::e42e:ce92:ca67:b62b 1337 50 100 100000
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
Success: send 50 byte to [2001:db8::e42e:ce92:ca67:b62b]:1337
> Packets received: 1
Packets received: 2
Packets received: 3
Packets received: 4
Packets received: 5
Packets received: 6
Packets received: 7
Packets received: 8
Packets received: 9
Packets received: 10
Packets received: 11
Packets received: 12
Packets received: 13
Packets received: 14
Packets received: 15
Packets received: 16
Packets received: 17
Packets received: 18
Packets received: 19
Packets received: 20
Packets received: 21
Packets received: 22
Packets received: 23
Packets received: 24
Packets received: 25
Packets received: 26
Packets received: 27
Packets received: 28
Packets received: 29
Packets received: 30
Packets received: 31
Packets received: 32
Packets received: 33
Packets received: 34
Packets received: 35
Packets received: 36
Packets received: 37
Packets received: 38
Packets received: 39
Packets received: 40
Packets received: 41
Packets received: 42
Packets received: 43
Packets received: 44
Packets received: 45
Packets received: 46
Packets received: 47
Packets received: 48
Packets received: 49
Packets received: 50
Packets received: 51
Packets received: 52
Packets received: 53
Packets received: 54
Packets received: 55
Packets received: 56
Packets received: 57
Packets received: 58
Packets received: 59
Packets received: 60
Packets received: 61
Packets received: 62
Packets received: 63
Packets received: 64
Packets received: 65
Packets received: 66
Packets received: 67
Packets received: 68
Packets received: 69
Packets received: 70
Packets received: 71
Packets received: 72
Packets received: 73
Packets received: 74
Packets received: 75
Packets received: 76
Packets received: 77
Packets received: 78
Packets received: 79
Packets received: 80
Packets received: 81
Packets received: 82
Packets received: 83
Packets received: 84
Packets received: 85
Packets received: 86
Packets received: 87
Packets received: 88
Packets received: 89
Packets received: 90
Packets received: 91
Packets received: 92
Packets received: 93
Packets received: 94
Packets received: 95
Packets received: 96
Packets received: 97
Packets received: 98
Packets received: 99
Packets received: 100
udp server stop
udp server stop
Success: stopped UDP server
> udp server start 1337
udp server start 1337
Success: started UDP server on port 1337
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
          inet6 addr: 2001:db8::a451:fab5:220d:a685  scope: global  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff0d:a685
          inet6 group: ff02::1a
          
           White-listed link layer addresses:
             0: 7A:94:05:FF:25:8D:E7:C3

          Statistics for Layer 2
            RX packets 55  bytes 3691
            TX packets 123 (Multicast: 19)  bytes 12647
            TX succeeded 123 errors 0
          Statistics for IPv6
            RX packets 19  bytes 1762
            TX packets 123 (Multicast: 19)  bytes 11710
            TX succeeded 123 errors 0

> udp send 2001:db8::a451:fab5:220d:a685 1337 50 100 100000
udp send 2001:db8::a451:fab5:220d:a685 1337 50 100 100000
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
Success: send 50 byte to [2001:db8::a451:fab5:220d:a685]:1337
> Packets received: 1
Packets received: 2
Packets received: 3
Packets received: 4
Packets received: 5
Packets received: 6
Packets received: 7
Packets received: 8
Packets received: 9
Packets received: 10
Packets received: 11
Packets received: 12
Packets received: 13
Packets received: 14
Packets received: 15
Packets received: 16
Packets received: 17
Packets received: 18
Packets received: 19
Packets received: 20
Packets received: 21
Packets received: 22
Packets received: 23
Packets received: 24
Packets received: 25
Packets received: 26
Packets received: 27
Packets received: 28
Packets received: 29
Packets received: 30
Packets received: 31
Packets received: 32
Packets received: 33
Packets received: 34
Packets received: 35
Packets received: 36
Packets received: 37
Packets received: 38
Packets received: 39
Packets received: 40
Packets received: 41
Packets received: 42
Packets received: 43
Packets received: 44
Packets received: 45
Packets received: 46
Packets received: 47
Packets received: 48
Packets received: 49
Packets received: 50
Packets received: 51
Packets received: 52
Packets received: 53
Packets received: 54
Packets received: 55
Packets received: 56
Packets received: 57
Packets received: 58
Packets received: 59
Packets received: 60
Packets received: 61
Packets received: 62
Packets received: 63
Packets received: 64
Packets received: 65
Packets received: 66
Packets received: 67
Packets received: 68
Packets received: 69
Packets received: 70
Packets received: 71
Packets received: 72
Packets received: 73
Packets received: 74
Packets received: 75
Packets received: 76
Packets received: 77
Packets received: 78
Packets received: 79
Packets received: 80
Packets received: 81
Packets received: 82
Packets received: 83
Packets received: 84
Packets received: 85
Packets received: 86
Packets received: 87
Packets received: 88
Packets received: 89
Packets received: 90
Packets received: 91
Packets received: 92
Packets received: 93
Packets received: 94
Packets received: 95
Packets received: 96
Packets received: 97
Packets received: 98
Packets received: 99
Packets received: 100
udp server stop
udp server stop
Success: stopped UDP server
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
  position of last byte used: 632
~ unused: 0x20001ebc (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001ebc, last byte: 0x20003ebc (size: 8192)
  position of last byte used: 472
~ unused: 0x20001ebc (next: (nil), size: 8192) ~
> 
```

