# 01. Task 03 - Unittests on native separated [tests-sock_util] [PASSED]
## Captured stdout call

```
Building application "tests_unittests" for "native" with MCU "native".

"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/boards/native
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/boards/native/drivers
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/core
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native/periph
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native/stdio_native
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers/periph_common
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/div
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/embunit
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/evtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/fmt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/luid
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/crosslayer/inet_csum
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netapi
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netreg
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/icmpv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ipv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ipv6/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ipv6/nib
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ndp
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pkt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf_static
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/sock
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/l2util
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/icmpv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/ipv4/addr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/ipv6/addr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/ipv6/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/sock
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/posix/inet
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/random
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/random/tinymt32
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/interactive_sync
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/xtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-sock_util
   text	   data	    bss	    dec	    hex	filename
  46972	    912	  52124	 100008	  186a8	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/tests_unittests.elf
r
/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/tests_unittests.elf /dev/ttyACM0 
RIOT native interrupts/signals initialized.
LED_RED_OFF
LED_GREEN_ON
RIOT native board initialized.
RIOT native hardware initialization complete.

main(): This is RIOT! (Version: 2021.10-devel-2021.07-branch)
Help: Press s to start test, r to print it is ready
READY
s
START
........................
OK (24 tests)


```

## Captured stderr call

```
/usr/bin/ld: /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/cpu/tramp.o: warning: relocation against `_native_saved_eip' in read-only section `.text'
/usr/bin/ld: warning: creating DT_TEXTREL in a PIE

```

