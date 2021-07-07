# 04. Task 10 (Experimental) - ICMPv6 echo with large payload (IPv6 fragmentation) [PASSED]
## Captured stdout call

```
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271550 --list saclay,m3,2 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
Building application "tests_gnrc_udp" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  88536	    184	  21100	 109820	  1acfc	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271550 --list saclay,m3,4 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/tests/gnrc_udp/bin/iotlab-m3/tests_gnrc_udp.bin
ssh -t lenders@saclay.iot-lab.info 'socat - tcp:m3-4.saclay.iot-lab.info:20000' 


> ifconfig
ifconfig
Iface  5  HWaddr: 65:0D  Channel: 26  Page: 0  NID: 0x23  PHY: O-QPSK 
          
          Long HWaddr: BE:B3:8D:16:33:2F:65:0D 
           TX-Power: 0dBm  State: IDLE  max. Retrans.: 3  CSMA Retries: 4 
          AUTOACK  ACK_REQ  CSMA  L2-PDU:102  MTU:1280  HL:64  RTR  
          6LO  IPHC  
          Source address length: 8
          Link type: wireless
          inet6 addr: fe80::bcb3:8d16:332f:650d  scope: link  VAL
          inet6 group: ff02::2
          inet6 group: ff02::1
          inet6 group: ff02::1:ff2f:650d
          
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
> ping6 fe80::bcb3:8d16:332f:650d -c 200 -i 600 -s 2048 -W 1000
ping6 fe80::bcb3:8d16:332f:650d -c 200 -i 600 -s 2048 -W 1000
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=0 ttl=64 rssi=-58 dBm time=263.050 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=1 ttl=64 rssi=-58 dBm time=267.181 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=2 ttl=64 rssi=-58 dBm time=279.600 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=3 ttl=64 rssi=-58 dBm time=280.905 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=4 ttl=64 rssi=-58 dBm time=276.812 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=5 ttl=64 rssi=-58 dBm time=273.601 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=6 ttl=64 rssi=-58 dBm time=282.856 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=7 ttl=64 rssi=-58 dBm time=277.043 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=8 ttl=64 rssi=-58 dBm time=290.838 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=9 ttl=64 rssi=-58 dBm time=290.485 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=10 ttl=64 rssi=-58 dBm time=270.647 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=12 ttl=64 rssi=-58 dBm time=274.222 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=13 ttl=64 rssi=-58 dBm time=269.748 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=14 ttl=64 rssi=-58 dBm time=282.547 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=15 ttl=64 rssi=-58 dBm time=285.368 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=16 ttl=64 rssi=-58 dBm time=265.593 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=17 ttl=64 rssi=-58 dBm time=280.311 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=18 ttl=64 rssi=-58 dBm time=280.271 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=19 ttl=64 rssi=-58 dBm time=280.894 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=20 ttl=64 rssi=-58 dBm time=279.351 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=21 ttl=64 rssi=-58 dBm time=283.193 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=22 ttl=64 rssi=-58 dBm time=277.373 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=23 ttl=64 rssi=-58 dBm time=278.371 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=24 ttl=64 rssi=-58 dBm time=286.961 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=25 ttl=64 rssi=-58 dBm time=282.198 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=26 ttl=64 rssi=-58 dBm time=270.714 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=27 ttl=64 rssi=-58 dBm time=276.461 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=28 ttl=64 rssi=-58 dBm time=274.197 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=29 ttl=64 rssi=-58 dBm time=278.274 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=30 ttl=64 rssi=-58 dBm time=288.875 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=31 ttl=64 rssi=-58 dBm time=268.147 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=32 ttl=64 rssi=-58 dBm time=285.726 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=33 ttl=64 rssi=-58 dBm time=284.436 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=34 ttl=64 rssi=-58 dBm time=273.946 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=35 ttl=64 rssi=-58 dBm time=281.892 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=36 ttl=64 rssi=-58 dBm time=276.786 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=37 ttl=64 rssi=-58 dBm time=271.331 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=38 ttl=64 rssi=-58 dBm time=279.983 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=39 ttl=64 rssi=-58 dBm time=268.145 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=40 ttl=64 rssi=-58 dBm time=271.283 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=41 ttl=64 rssi=-58 dBm time=282.837 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=42 ttl=64 rssi=-58 dBm time=287.898 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=43 ttl=64 rssi=-58 dBm time=278.993 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=44 ttl=64 rssi=-58 dBm time=279.283 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=45 ttl=64 rssi=-58 dBm time=264.633 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=46 ttl=64 rssi=-58 dBm time=289.232 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=47 ttl=64 rssi=-58 dBm time=274.508 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=48 ttl=64 rssi=-58 dBm time=276.767 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=49 ttl=64 rssi=-58 dBm time=292.730 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=50 ttl=64 rssi=-58 dBm time=272.932 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=52 ttl=64 rssi=-58 dBm time=262.724 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=53 ttl=64 rssi=-58 dBm time=274.179 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=54 ttl=64 rssi=-58 dBm time=268.134 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=55 ttl=64 rssi=-58 dBm time=273.919 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=56 ttl=64 rssi=-58 dBm time=259.832 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=57 ttl=64 rssi=-58 dBm time=273.227 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=58 ttl=64 rssi=-58 dBm time=286.317 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=59 ttl=64 rssi=-58 dBm time=281.238 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=60 ttl=64 rssi=-58 dBm time=279.689 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=61 ttl=64 rssi=-58 dBm time=283.796 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=62 ttl=64 rssi=-58 dBm time=271.998 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=63 ttl=64 rssi=-58 dBm time=258.212 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=64 ttl=64 rssi=-58 dBm time=272.307 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=65 ttl=64 rssi=-58 dBm time=279.363 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=66 ttl=64 rssi=-58 dBm time=272.954 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=67 ttl=64 rssi=-58 dBm time=275.496 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=68 ttl=64 rssi=-58 dBm time=279.968 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=69 ttl=64 rssi=-58 dBm time=282.493 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=70 ttl=64 rssi=-58 dBm time=281.923 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=71 ttl=64 rssi=-58 dBm time=276.467 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=72 ttl=64 rssi=-58 dBm time=285.712 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=73 ttl=64 rssi=-58 dBm time=276.801 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=74 ttl=64 rssi=-58 dBm time=270.662 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=75 ttl=64 rssi=-58 dBm time=279.668 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=76 ttl=64 rssi=-58 dBm time=281.893 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=77 ttl=64 rssi=-58 dBm time=292.130 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=78 ttl=64 rssi=-58 dBm time=277.742 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=79 ttl=64 rssi=-58 dBm time=278.664 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=80 ttl=64 rssi=-58 dBm time=284.765 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=82 ttl=64 rssi=-58 dBm time=278.372 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=83 ttl=64 rssi=-58 dBm time=284.473 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=84 ttl=64 rssi=-58 dBm time=266.536 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=85 ttl=64 rssi=-58 dBm time=279.653 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=86 ttl=64 rssi=-58 dBm time=272.281 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=87 ttl=64 rssi=-58 dBm time=283.832 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=88 ttl=64 rssi=-58 dBm time=280.271 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=89 ttl=64 rssi=-58 dBm time=282.863 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=90 ttl=64 rssi=-58 dBm time=286.025 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=91 ttl=64 rssi=-58 dBm time=279.631 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=92 ttl=64 rssi=-58 dBm time=283.168 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=93 ttl=64 rssi=-58 dBm time=277.435 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=94 ttl=64 rssi=-58 dBm time=278.366 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=95 ttl=64 rssi=-58 dBm time=277.391 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=96 ttl=64 rssi=-58 dBm time=261.129 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=97 ttl=64 rssi=-58 dBm time=279.639 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=98 ttl=64 rssi=-58 dBm time=281.866 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=99 ttl=64 rssi=-58 dBm time=282.191 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=101 ttl=64 rssi=-58 dBm time=284.133 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=102 ttl=64 rssi=-58 dBm time=277.374 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=103 ttl=64 rssi=-58 dBm time=282.857 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=104 ttl=64 rssi=-58 dBm time=294.338 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=105 ttl=64 rssi=-58 dBm time=262.115 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=106 ttl=64 rssi=-58 dBm time=271.914 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=107 ttl=64 rssi=-58 dBm time=285.705 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=108 ttl=64 rssi=-58 dBm time=289.276 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=109 ttl=64 rssi=-58 dBm time=268.158 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=110 ttl=64 rssi=-58 dBm time=285.389 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=111 ttl=64 rssi=-58 dBm time=269.119 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=112 ttl=64 rssi=-58 dBm time=289.544 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=113 ttl=64 rssi=-58 dBm time=289.604 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=114 ttl=64 rssi=-58 dBm time=271.987 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=115 ttl=64 rssi=-58 dBm time=274.841 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=116 ttl=64 rssi=-58 dBm time=278.305 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=117 ttl=64 rssi=-58 dBm time=288.908 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=118 ttl=64 rssi=-58 dBm time=277.035 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=119 ttl=64 rssi=-58 dBm time=286.999 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=120 ttl=64 rssi=-58 dBm time=267.495 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=121 ttl=64 rssi=-58 dBm time=277.143 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=122 ttl=64 rssi=-58 dBm time=286.035 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=123 ttl=64 rssi=-58 dBm time=273.229 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=124 ttl=64 rssi=-58 dBm time=270.721 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=125 ttl=64 rssi=-58 dBm time=280.611 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=126 ttl=64 rssi=-58 dBm time=280.231 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=127 ttl=64 rssi=-58 dBm time=279.691 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=128 ttl=64 rssi=-58 dBm time=286.683 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=129 ttl=64 rssi=-58 dBm time=276.734 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=130 ttl=64 rssi=-58 dBm time=268.812 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=131 ttl=64 rssi=-58 dBm time=276.131 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=132 ttl=64 rssi=-58 dBm time=283.821 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=133 ttl=64 rssi=-58 dBm time=265.221 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=134 ttl=64 rssi=-58 dBm time=284.089 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=135 ttl=64 rssi=-58 dBm time=276.388 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=136 ttl=64 rssi=-58 dBm time=289.599 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=137 ttl=64 rssi=-58 dBm time=278.641 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=138 ttl=64 rssi=-58 dBm time=272.907 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=139 ttl=64 rssi=-58 dBm time=275.157 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=140 ttl=64 rssi=-58 dBm time=273.544 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=141 ttl=64 rssi=-58 dBm time=276.130 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=142 ttl=64 rssi=-58 dBm time=285.068 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=143 ttl=64 rssi=-58 dBm time=271.973 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=144 ttl=64 rssi=-58 dBm time=279.936 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=145 ttl=64 rssi=-58 dBm time=282.865 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=146 ttl=64 rssi=-58 dBm time=261.790 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=147 ttl=64 rssi=-58 dBm time=268.731 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=148 ttl=64 rssi=-58 dBm time=266.881 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=149 ttl=64 rssi=-58 dBm time=271.617 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=150 ttl=64 rssi=-58 dBm time=269.425 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=151 ttl=64 rssi=-58 dBm time=274.521 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=152 ttl=64 rssi=-58 dBm time=288.864 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=153 ttl=64 rssi=-58 dBm time=281.943 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=154 ttl=64 rssi=-58 dBm time=282.838 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=155 ttl=64 rssi=-58 dBm time=260.490 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=156 ttl=64 rssi=-58 dBm time=268.815 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=157 ttl=64 rssi=-58 dBm time=264.959 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=158 ttl=64 rssi=-58 dBm time=284.448 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=159 ttl=64 rssi=-58 dBm time=272.289 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=160 ttl=64 rssi=-58 dBm time=272.981 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=161 ttl=64 rssi=-58 dBm time=282.486 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=162 ttl=64 rssi=-58 dBm time=282.514 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=163 ttl=64 rssi=-58 dBm time=275.836 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=164 ttl=64 rssi=-58 dBm time=284.770 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=165 ttl=64 rssi=-58 dBm time=283.477 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=166 ttl=64 rssi=-58 dBm time=275.143 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=167 ttl=64 rssi=-58 dBm time=280.936 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=168 ttl=64 rssi=-58 dBm time=275.513 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=169 ttl=64 rssi=-58 dBm time=275.518 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=171 ttl=64 rssi=-58 dBm time=285.407 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=172 ttl=64 rssi=-58 dBm time=277.429 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=173 ttl=64 rssi=-58 dBm time=286.042 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=174 ttl=64 rssi=-58 dBm time=281.569 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=175 ttl=64 rssi=-58 dBm time=281.572 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=176 ttl=64 rssi=-58 dBm time=276.165 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=177 ttl=64 rssi=-58 dBm time=270.350 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=178 ttl=64 rssi=-58 dBm time=278.045 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=179 ttl=64 rssi=-58 dBm time=276.178 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=180 ttl=64 rssi=-58 dBm time=292.096 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=181 ttl=64 rssi=-58 dBm time=274.828 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=182 ttl=64 rssi=-58 dBm time=283.834 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=183 ttl=64 rssi=-58 dBm time=282.509 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=184 ttl=64 rssi=-58 dBm time=283.815 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=185 ttl=64 rssi=-58 dBm time=279.293 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=186 ttl=64 rssi=-58 dBm time=273.250 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=187 ttl=64 rssi=-58 dBm time=282.808 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=188 ttl=64 rssi=-58 dBm time=269.782 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=189 ttl=64 rssi=-58 dBm time=269.111 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=190 ttl=64 rssi=-58 dBm time=278.994 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=191 ttl=64 rssi=-58 dBm time=280.863 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=192 ttl=64 rssi=-58 dBm time=281.896 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=193 ttl=64 rssi=-58 dBm time=274.874 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=194 ttl=64 rssi=-58 dBm time=282.520 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=195 ttl=64 rssi=-58 dBm time=279.966 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=196 ttl=64 rssi=-58 dBm time=283.464 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=197 ttl=64 rssi=-58 dBm time=286.976 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=198 ttl=64 rssi=-58 dBm time=263.371 ms
2056 bytes from fe80::bcb3:8d16:332f:650d%5: icmp_seq=199 ttl=64 rssi=-58 dBm time=276.740 ms

--- fe80::bcb3:8d16:332f:650d PING statistics ---
200 packets transmitted, 195 packets received, 2% packet loss
round-trip min/avg/max = 258.212/277.916/294.338 ms
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 7976
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> pktbuf
pktbuf
packet buffer: first byte: 0x20001e5c, last byte: 0x20003e5c (size: 8192)
  position of last byte used: 7976
~ unused: 0x20001e5c (next: (nil), size: 8192) ~
> 
```

