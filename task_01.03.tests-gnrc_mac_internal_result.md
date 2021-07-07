# 01. Task 03 - Unittests on native separated [tests-gnrc_mac_internal] [PASSED]
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
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/link_layer/mac
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netapi
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netreg
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pkt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf_static
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/priority_pktqueue
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/csma_sender
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/l2util
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/random
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/random/tinymt32
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/interactive_sync
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/xtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_mac_internal
   text	   data	    bss	    dec	    hex	filename
  43935	    716	  58148	 102799	  1918f	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/tests_unittests.elf
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
...
OK (3 tests)


```

## Captured stderr call

```
/usr/bin/ld: /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/cpu/tramp.o: warning: relocation against `_native_saved_eip' in read-only section `.text'
/usr/bin/ld: warning: creating DT_TEXTREL in a PIE

```

