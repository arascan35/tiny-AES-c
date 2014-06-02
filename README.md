### Tiny AES128 in C

This is a small and portable implementation of the AES128 algorithm implemented in C.

The module uses just a bit more than 200 bytes of RAM and 1K ROM when compiled for ARM (YMMV).

It is the smallest implementation in C I've seen yet, but do contact me if you know of something smaller (or have improvements to the code here).


I've successfully used the code on 64bit x86, 32bit ARM and 8 bit AVR platforms.


GCC size output when compiled for ARM:



    $ arm-none-eabi-gcc -Os -c -mthumb aes.c -o aes.o
    $ size aes.o
       text    data     bss     dec     hex filename
       1107       0     204    1311     51f aes.o


I am using Mentor Graphics ARM toolchain:


    $ arm-none-eabi-gcc --version
    arm-none-eabi-gcc (GNU Tools for ARM Embedded Processors) 4.8.3 20131129 (release) [ARM/embedded-4_8-branch revision 205641]
    Copyright (C) 2013 Free Software Foundation, Inc.
    This is free software; see the source for copying conditions.  There is NO
    warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.




The implementation is verified against the data in:

[National Institute of Standards and Technology Special Publication 800-38A 2001 ED](http://csrc.nist.gov/publications/nistpubs/800-38a/sp800-38a.pdf) Appendix F: Example Vectors for Modes of Operation of the AES.



