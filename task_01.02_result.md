# 01. Task 02 - Unittests on native [FAILED]
## Failures

```
nodes = [<riotctrl.ctrl.RIOTCtrl object at 0x7fc84699fe80>], log_nodes = True, riotbase = '/home/mlenders/Repositories/RIOT-OS/RIOT'

    @pytest.mark.parametrize('nodes',
                             [pytest.param(['native'])],
                             indirect=['nodes'])
    def test_task02(nodes, log_nodes, riotbase):
>       run_unittests('all', nodes, log_nodes, os.path.join(riotbase, APP))

01-ci/test_spec01.py:31: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
01-ci/test_spec01.py:19: in run_unittests
    node.make_run(
.tox/test/lib/python3.9/site-packages/riotctrl/ctrl.py:178: in make_run
    return subprocess.run(command, env=self.env, *runargs, **runkwargs)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

input = None, capture_output = False, timeout = None, check = True
popenargs = (['make', '--no-print-directory', '-C', '/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests', 'all', 'flash-only', ...],)
kwargs = {'env': {'BOARD': 'native', 'HOME': '/home/mlenders', 'LANG': 'en_US.UTF-8', 'PATH': '/home/mlenders/Repositories/RIOT.../usr/bin/core_perl:/home/mlenders/.local/bin:/home/mlenders/.gem/ruby/2.7.0/bin', ...}, 'stderr': None, 'stdout': None}
process = <Popen: returncode: 2 args: ['make', '--no-print-directory', '-C', '/home/ml...>, stdout = None, stderr = None, retcode = 2

    def run(*popenargs,
            input=None, capture_output=False, timeout=None, check=False, **kwargs):
        """Run command with arguments and return a CompletedProcess instance.
    
        The returned instance will have attributes args, returncode, stdout and
        stderr. By default, stdout and stderr are not captured, and those attributes
        will be None. Pass stdout=PIPE and/or stderr=PIPE in order to capture them.
    
        If check is True and the exit code was non-zero, it raises a
        CalledProcessError. The CalledProcessError object will have the return code
        in the returncode attribute, and output & stderr attributes if those streams
        were captured.
    
        If timeout is given, and the process takes too long, a TimeoutExpired
        exception will be raised.
    
        There is an optional argument "input", allowing you to
        pass bytes or a string to the subprocess's stdin.  If you use this argument
        you may not also use the Popen constructor's "stdin" argument, as
        it will be used internally.
    
        By default, all communication is in bytes, and therefore any "input" should
        be bytes, and the stdout and stderr will be bytes. If in text mode, any
        "input" should be a string, and stdout and stderr will be strings decoded
        according to locale encoding, or by "encoding" if set. Text mode is
        triggered by setting any of text, encoding, errors or universal_newlines.
    
        The other arguments are the same as for the Popen constructor.
        """
        if input is not None:
            if kwargs.get('stdin') is not None:
                raise ValueError('stdin and input arguments may not both be used.')
            kwargs['stdin'] = PIPE
    
        if capture_output:
            if kwargs.get('stdout') is not None or kwargs.get('stderr') is not None:
                raise ValueError('stdout and stderr arguments may not be used '
                                 'with capture_output.')
            kwargs['stdout'] = PIPE
            kwargs['stderr'] = PIPE
    
        with Popen(*popenargs, **kwargs) as process:
            try:
                stdout, stderr = process.communicate(input, timeout=timeout)
            except TimeoutExpired as exc:
                process.kill()
                if _mswindows:
                    # Windows accumulates the output in a single blocking
                    # read() call run on child threads, with the timeout
                    # being done in a join() on those threads.  communicate()
                    # _after_ kill() is required to collect that and add it
                    # to the exception.
                    exc.stdout, exc.stderr = process.communicate()
                else:
                    # POSIX _communicate already populated the output so
                    # far into the TimeoutExpired exception.
                    process.wait()
                raise
            except:  # Including KeyboardInterrupt, communicate handled that.
                process.kill()
                # We don't call process.wait() as .__exit__ does that for us.
                raise
            retcode = process.poll()
            if check and retcode:
>               raise CalledProcessError(retcode, process.args,
                                         output=stdout, stderr=stderr)
E               subprocess.CalledProcessError: Command '['make', '--no-print-directory', '-C', '/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests', 'all', 'flash-only', 'test']' returned non-zero exit status 2.

/usr/lib/python3.9/subprocess.py:528: CalledProcessError
```

## Captured stdout call

```
Building application "tests_unittests" for "native" with MCU "native".

"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/boards/native
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/boards/native/drivers
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/core
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native/mtd
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native/periph
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native/stdio_native
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/cpu/native/vfs
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers/mtd
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers/periph_common
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers/rtt_rtc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers/saul
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/drivers/sht1x
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/analog_util
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/base64
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/bitfield
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/bloom
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/checksum
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/clif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/color
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/crypto
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/div
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/ecc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/embunit
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/event
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/evtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/fmt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/frac
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/fs/constfs
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/hashes
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/luid
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/matstat
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/application_layer/gcoap
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/application_layer/nanocoap
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/ble/bluetil
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/ble/bluetil/bluetil_addr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/credman
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/crosslayer/inet_csum
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/crosslayer/netopt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/link_layer/mac
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netapi
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netif/pktq
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/netreg
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/icmpv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ipv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ipv6/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ipv6/nib
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/ndp
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan/ctx
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan/frag/fb
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan/frag/vrb
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/network_layer/sixlowpan/nd
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pkt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/pktbuf_static
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/priority_pktqueue
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/sock
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/sock/udp
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/gnrc/transport_layer/udp
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/csma_sender
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/ieee802154
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/link_layer/l2util
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/netif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/fib
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/icmpv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/ipv4/addr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/ipv6/addr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/ipv6/hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/network_layer/sixlowpan
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/sock
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/sock/async/event
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/net/transport_layer/udp
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/od
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/phydat
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/posix/inet
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/random
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/random/tinymt32
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/saul_reg
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/seq
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/interactive_sync
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/result_output
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/test_utils/result_output/check
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/timex
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/tsrb
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/universal_address
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/uri_parser
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/uuid
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/vfs
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/xtimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/sys/ztimer
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-analog_util
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-base64
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-bcd
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-bitfield
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-bloom
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-bluetil
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-checksum
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-clif
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-color
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-core
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-credman
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-div
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ecc
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-fib
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-fib_sr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-fmt
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-frac
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gcoap
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_ipv6
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_ipv6_hdr
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_ipv6_nib
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_mac_internal
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_netif_pktq
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_sixlowpan_frag_vrb
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-gnrc_udp
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-hashes
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ieee802154
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-inet_csum
"make" -C /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr

```

## Captured stderr call

```
In file included from [01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/sys/include/embUnit/embUnit.h:47[m[K,
                 from [01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr/tests-ipv4_addr.c:17[m[K:
[01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr/tests-ipv4_addr.c:[m[K In function ‘[01m[Ktest_ipv4_addr_to_str__result_NULL[m[K’:
[01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr/tests-ipv4_addr.c:59:22:[m[K [01;31m[Kerror: [m[K‘[01m[Ka[m[K’ may be used uninitialized [[01;31m[K-Werror=maybe-uninitialized[m[K]
   59 |     TEST_ASSERT_NULL(ipv4_addr_to_str(NULL, &a, IPV4_ADDR_MAX_STR_LEN));
[01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/sys/include/embUnit/AssertImpl.h:70:47:[m[K [01;36m[Knote: [m[Kin definition of macro ‘[01m[KTEST_ASSERT_NULL[m[K’
   70 |         __typeof__(pointer_) ____pointer__ = ([01;36m[Kpointer_[m[K); \
      |                                               [01;36m[K^~~~~~~~[m[K
In file included from [01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr/tests-ipv4_addr.c:20[m[K:
[01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/sys/include/net/ipv4/addr.h:72:7:[m[K [01;36m[Knote: [m[Kby argument 2 of type ‘[01m[Kconst ipv4_addr_t *[m[K’ to ‘[01m[Kipv4_addr_to_str[m[K’ declared here
   72 | char *[01;36m[Kipv4_addr_to_str[m[K(char *result, const ipv4_addr_t *addr, uint8_t result_len);
      |       [01;36m[K^~~~~~~~~~~~~~~~[m[K
[01m[K/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr/tests-ipv4_addr.c:57:17:[m[K [01;36m[Knote: [m[K‘[01m[Ka[m[K’ declared here
   57 |     ipv4_addr_t [01;36m[Ka[m[K;
      |                 [01;36m[K^[m[K
cc1: all warnings being treated as errors
make[2]: *** [/home/mlenders/Repositories/RIOT-OS/RIOT/Makefile.base:131: /home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/bin/native/tests-ipv4_addr/tests-ipv4_addr.o] Error 1
make[1]: *** [/home/mlenders/Repositories/RIOT-OS/RIOT/Makefile.base:31: ALL--/home/mlenders/Repositories/RIOT-OS/RIOT/tests/unittests/tests-ipv4_addr] Error 2
make: *** [/home/mlenders/Repositories/RIOT-OS/RIOT/Makefile.include:675: application_tests_unittests.module] Error 2

```

