# 06. Task 06 - Empty UDP on iotlab-m3 [PASSED]
## Captured stdout call

```
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271559 --list saclay,m3,10 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271559 --list saclay,m3,11 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-11.saclay.iot-lab.info:20000' 


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
          
          Statistics for Layer 2
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 86
            TX succeeded 2 errors 0
          Statistics for IPv6
            RX packets 0  bytes 0
            TX packets 2 (Multicast: 2)  bytes 128
            TX succeeded 2 errors 0

> ifconfig 5 set channel 26
ifconfig 5 set channel 26
success: set channel on interface 5 to 26
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
          
          Statistics for Layer 2
            RX packets 2  bytes 86
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 2  bytes 128
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ifconfig 5 set channel 26
ifconfig 5 set channel 26
success: set channel on interface 5 to 26
> udp server start 1337
udp server start 1337
Success: started UDP server on port 1337
> udp send fe80::e4d3:6fec:df36:bbe 1337 0 100 100000
udp send fe80::e4d3:6fec:df36:bbe 1337 0 100 100000
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
Success: send 0 byte to [fe80::e4d3:6fec:df36:bbe]:1337
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
          
          Statistics for Layer 2
            RX packets 3  bytes 129
            TX packets 104 (Multicast: 4)  bytes 3172
            TX succeeded 104 errors 0
          Statistics for IPv6
            RX packets 3  bytes 192
            TX packets 104 (Multicast: 4)  bytes 5056
            TX succeeded 104 errors 0

> ifconfig 5 set channel 26
ifconfig 5 set channel 26
success: set channel on interface 5 to 26
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
          
          Statistics for Layer 2
            RX packets 101  bytes 3043
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 101  bytes 5664
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ifconfig 5 set channel 26
ifconfig 5 set channel 26
success: set channel on interface 5 to 26
> udp server start 1337
udp server start 1337
Success: started UDP server on port 1337
> udp send fe80::7894:5ff:258d:e7c3 1337 0 100 100000
udp send fe80::7894:5ff:258d:e7c3 1337 0 100 100000
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
Success: send 0 byte to [fe80::7894:5ff:258d:e7c3]:1337
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
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 272
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 272
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> 
```

