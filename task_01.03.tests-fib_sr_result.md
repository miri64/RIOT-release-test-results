# 01. Task 03 - Unittests on native separated [tests-fib_sr] [PASSED]
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
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/fib
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/interactive_sync
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/universal_address
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/xtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-fib_sr
   text	   data	    bss	    dec	    hex	filename
  52274	    820	  56492	 109586	  1ac12	/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/tests_unittests.elf
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
............
OK (12 tests)


```

## Captured stderr call

```
/usr/bin/ld: /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/cpu/tramp.o: warning: relocation against `_native_saved_eip' in read-only section `.text'
/usr/bin/ld: warning: creating DT_TEXTREL in a PIE

```

