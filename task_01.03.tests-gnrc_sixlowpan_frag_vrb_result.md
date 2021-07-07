# 01. Task 03 - Unittests on native separated [tests-gnrc_sixlowpan_frag_vrb] [PASSED]
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
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/fmt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netapi
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netreg
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan/frag/fb
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan/frag/vrb
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pkt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf_static
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/l2util
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/interactive_sync
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/xtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_sixlowpan_frag_vrb
   text	   data	    bss	    dec	    hex	filename
  35995	    808	  52708	  89511	  15da7	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/tests_unittests.elf
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
.......
OK (7 tests)


```

## Captured stderr call

```
/usr/bin/ld: /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/cpu/tramp.o: warning: relocation against `_native_saved_eip' in read-only section `.text'
/usr/bin/ld: warning: creating DT_TEXTREL in a PIE

```

