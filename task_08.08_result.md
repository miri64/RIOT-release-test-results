# 08. Task 08 - UDP between GNRC and lwIP on iotlab-m3 [PASSED]
## Captured stdout call

```
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90304	    188	  18996	 109488	  1abb0	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271566 --list saclay,m3,10 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
Building application "tests_lwip" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  99044	    160	  18724	 117928	  1cca8	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/lwip/bin/iotlab-m3/tests_lwip.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271566 --list saclay,m3,11 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/lwip/bin/iotlab-m3/tests_lwip.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-10.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  6  HWaddr: 67:C3  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
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
          
          Statistics for Layer 2
            RX packets 2  bytes 91
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-11.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface L60 HWaddr: e6:d3:6f:ec:df:36:0b:be Link: up State: up
        Link type: wireless
        inet6 addr: fe80:0:0:0:e4d3:6fec:df36:bbe scope: link
> udp server start 61616
udp server start 61616
Success: started UDP server on port 61616
> udp send [fe80::7894:5ff:258d:e7c3]:61616 012345678abcdef
udp send [fe80::7894:5ff:258d:e7c3]:61616 012345678abcdef
Success: send 8 byte over UDP to [fe80::7894:5ff:258d:e7c3]:61616
> PKTDUMP: data received:
~~ SNIP  0 - size:   8 byte, type: NETTYPE_UNDEF (0)
00000000  01  23  45  67  8A  BC  DE  F0
~~ SNIP  1 - size:   8 byte, type: NETTYPE_UDP (4)
   src-port: 49153  dst-port: 61616
   length: 16  cksum: 0xd648
~~ SNIP  2 - size:  40 byte, type: NETTYPE_IPV6 (2)
traffic class: 0x00 (ECN: 0x0, DSCP: 0x00)
flow label: 0x00000
length: 16  next header: 17  hop limit: 255
source address: fe80::e4d3:6fec:df36:bbe
destination address: fe80::7894:5ff:258d:e7c3
~~ SNIP  3 - size:  24 byte, type: NETTYPE_NETIF (-1)
if_pid: 6  rssi: -46  lqi: 255
flags: 0x0
src_l2addr: E6:D3:6F:EC:DF:36:0B:BE
dst_l2addr: 7A:94:05:FF:25:8D:E7:C3
~~ PKT    -  4 snips, total size:  80 byte
udp server stop
udp server stop
Success: stopped UDP server
> udp server start 61617
udp server start 61617
Success: started UDP server on port 61617
> udp send fe80:0:0:0:e4d3:6fec:df36:bbe 61617 01234567 1 1000000
udp send fe80:0:0:0:e4d3:6fec:df36:bbe 61617 01234567 1 1000000
Success: sent 8 byte(s) to [fe80:0:0:0:e4d3:6fec:df36:bbe]:61617
> Received UDP data from [fe80::7894:5ff:258d:e7c3]:61617
00000000  30  31  32  33  34  35  36  37

```

