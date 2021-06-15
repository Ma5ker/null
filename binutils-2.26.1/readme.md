to replay, run `./size ./poc`

crash info:

```
sec@ubuntu160432:~/tmp/binutils/binutils-2.26.1/binutils$ ./size ../../poc 
./size: ../../poc: invalid SHT_GROUP entry
=================================================================
==30246==ERROR: AddressSanitizer: heap-buffer-overflow on address 0xb4942ef8 at pc 0x080c3e86 bp 0xbfffe6b8 sp 0xbfffe6a8
READ of size 4 at 0xb4942ef8 thread T0
    #0 0x80c3e85 in bfd_elf_get_elf_syms (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x80c3e85)
    #1 0x80c4bd7 in group_signature (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x80c4bd7)
    #2 0x80c61ea in setup_group (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x80c61ea)
    #3 0x80c7e02 in _bfd_elf_make_section_from_shdr (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x80c7e02)
    #4 0x80d2c50 in bfd_section_from_shdr (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x80d2c50)
    #5 0x80b90d8 in bfd_elf32_object_p (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x80b90d8)
    #6 0x8067683 in bfd_check_format_matches (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x8067683)
    #7 0x804af8c in display_bfd (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x804af8c)
    #8 0x804b372 in display_file (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x804b372)
    #9 0x804a9c4 in main (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x804a9c4)
    #10 0xb78bc646 in __libc_start_main (/lib/i386-linux-gnu/libc.so.6+0x18646)
    #11 0x804a0a0  (/home/sec/tmp/binutils/binutils-2.26.1/binutils/size+0x804a0a0)

AddressSanitizer can not describe address in more detail (wild memory access suspected).
SUMMARY: AddressSanitizer: heap-buffer-overflow ??:0 bfd_elf_get_elf_syms
Shadow bytes around the buggy address:
  0x36928580: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x36928590: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x369285a0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x369285b0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x369285c0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
=>0x369285d0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa[fa]
  0x369285e0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x369285f0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x36928600: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x36928610: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x36928620: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
Shadow byte legend (one shadow byte represents 8 application bytes):
  Addressable:           00
  Partially addressable: 01 02 03 04 05 06 07 
  Heap left redzone:       fa
  Heap right redzone:      fb
  Freed heap region:       fd
  Stack left redzone:      f1
  Stack mid redzone:       f2
  Stack right redzone:     f3
  Stack partial redzone:   f4
  Stack after return:      f5
  Stack use after scope:   f8
  Global redzone:          f9
  Global init order:       f6
  Poisoned by user:        f7
  Container overflow:      fc
  Array cookie:            ac
  Intra object redzone:    bb
  ASan internal:           fe
==30246==ABORTING
sec@ubuntu160432:~/tmp/binutils/binutils-2.26.1/binutils$ 
```
