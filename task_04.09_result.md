# 04. Task 09 - ICMPv6 stress test on iotlab-m3 [FAILED]
## Failures

```
riot_ctrl = <function riot_ctrl.<locals>.ctrl at 0x7fdf6a28b430>

    @pytest.mark.iotlab_creds
    # nodes passed to riot_ctrl fixture
    @pytest.mark.parametrize('nodes',
                             [pytest.param(['iotlab-m3', 'iotlab-m3',
                                            'iotlab-m3'])],
                             indirect=['nodes'])
    def test_task09(riot_ctrl):
        nodes = (
            riot_ctrl(0, APP, Shell, modules=["gnrc_pktbuf_cmd"]),
            riot_ctrl(1, APP, Shell, modules=["gnrc_pktbuf_cmd"]),
>           riot_ctrl(2, APP, Shell, modules=["gnrc_pktbuf_cmd"]),
        )

04-single-hop-6lowpan-icmp/test_spec04.py:243: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
conftest.py:350: in ctrl
    node.make_run(['flash'], check=True,
.tox/test/lib/python3.9/site-packages/riotctrl/ctrl.py:178: in make_run
    return subprocess.run(command, env=self.env, *runargs, **runkwargs)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

input = None, capture_output = False, timeout = None, check = True
popenargs = (['make', '--no-print-directory', '-C', '/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking', 'flash'],)
kwargs = {'env': {'BOARD': 'iotlab-m3', 'HOME': '/home/mlenders', 'IOTLAB_EXP_ID': '271549', 'IOTLAB_NODE': 'm3-12.saclay.iot-lab.info', ...}, 'stderr': None, 'stdout': None}
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
E               subprocess.CalledProcessError: Command '['make', '--no-print-directory', '-C', '/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking', 'flash']' returned non-zero exit status 2.

/usr/lib/python3.9/subprocess.py:528: CalledProcessError
```

## Captured stdout call

```
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271549 --list saclay,m3,1 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271549 --list saclay,m3,9 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin
Building application "gnrc_networking" for "iotlab-m3" with MCU "stm32".

   text	   data	    bss	    dec	    hex	filename
  90856	    188	  18996	 110040	  1add8	/home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.elf
iotlab-node --jmespath='keys(@)[0]' --format='lambda ret: exit(int(ret))' --id 271549 --list saclay,m3,12 --flash /home/mlenders/Repositories/RIOT-OS/RIOT/examples/gnrc_networking/bin/iotlab-m3/gnrc_networking.bin

```

## Captured stderr call

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

