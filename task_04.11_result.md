# 04. Task 11 (Experimental) - ICMPv6 stress test on nrf802154 [PASSED]
## Captured stdout call

```
Building application "gnrc_networking" for "nrf52840dk" with MCU "nrf52".

   text	   data	    bss	    dec	    hex	filename
  89788	    200	  19404	 109392	  1ab50	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/nrf52840dk/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271551 --list saclay,nrf52840dk,10 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/nrf52840dk/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271551 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271551 --list saclay,m3,12 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:nrf52840dk-10.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  6  HWaddr: 15:8F  Channel: 26  NID: 0x23  PHY: O-QPSK 
          Long HWaddr: A6:52:AD:7D:44:2C:95:8F 
           State: IDLE 
          ACK_REQ  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::a452:ad7d:442c:958f  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff2c:958f
          
          Statistics for Layer 2
            RX packets 3  bytes 129
            TX packets 4 (Multicast: 4)  bytes 0
            TX succeeded 4 errors 0
          Statistics for IPv6
            RX packets 3  bytes 192
            TX packets 4 (Multicast: 4)  bytes 256
            TX succeeded 4 errors 0

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
            RX packets 4  bytes 172
            TX packets 3 (Multicast: 3)  bytes 129
            TX succeeded 3 errors 0
          Statistics for IPv6
            RX packets 4  bytes 256
            TX packets 3 (Multicast: 3)  bytes 192
            TX succeeded 3 errors 0

> ifconfig 6 set channel 26
ifconfig 6 set channel 26
success: set channel on interface 6 to 26
> ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-12.saclay.iot-lab.info:20000' 


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
            RX packets 1  bytes 43
            TX packets 2 (Multicast: 2)  bytes 86
            TX succeeded 2 errors 0
          Statistics for IPv6
            RX packets 1  bytes 64
            TX packets 2 (Multicast: 2)  bytes 128
            TX succeeded 2 errors 0

> ifconfig 6 set channel 26
ifconfig 6 set channel 26
success: set channel on interface 6 to 26
> ping6 fe80::a452:ad7d:442c:958f -c 200 -i 0 -s 1232 -W 1000
ping6 fe80::a452:ad7d:442c:958f -c 200 -i 0 -s 1232 -W 1000
ping6 fe80::a452:ad7d:442c:958f -c 200 -i 0 -s 1232 -W 1000
ping6 fe80::a452:ad7d:442c:958f -c 200 -i 0 -s 1232 -W 1000

--- fe80::a452:ad7d:442c:958f PING statistics ---
200 packets transmitted, 0 packets received, 100% packet loss
> 
--- fe80::a452:ad7d:442c:958f PING statistics ---
200 packets transmitted, 0 packets received, 100% packet loss
> pktbuf
pktbuf
packet buffer: first byte: 0x200018ac, last byte: 0x200030ac (size: 6144)
  position of last byte used: 5728
~ unused: 0x200018ac (next: (nil), size: 6144) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 1504
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x200017b0, last byte: 0x20002fb0 (size: 6144)
  position of last byte used: 1504
~ unused: 0x200017b0 (next: (nil), size: 6144) ~
> 
```

