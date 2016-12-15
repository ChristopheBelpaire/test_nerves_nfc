# TestNervesNfc

Build fail on OSX with
  * Install dependencies with `mix deps.get`
  * Create firmware with `NERVES_TARGET=rpi3 MAKE_HOST=arm-unknown-linux-gnu mix compile nerves_io_nfc`

It fail to compile with:

```
In file included from nfc-emulate-forum-tag4.c:70:0:
/Users/christophebelpaire/selinko/test_nerves_nfc/_build/rpi3/dev/nerves/system/staging/usr/include/stdint.h:49:28: warning: redefinition of typedef 'uint16_t' [-Wpedantic]
 typedef unsigned short int uint16_t;
                            ^
<command-line>:0:11: note: previous declaration of 'uint16_t' was here
/Users/christophebelpaire/selinko/test_nerves_nfc/_build/rpi3/dev/nerves/system/staging/usr/include/sys/types.h:190:24: note: in expansion of macro 'u_int16_t'
   typedef unsigned int u_int##N##_t __attribute__ ((__mode__ (MODE)))
                        ^
/Users/christophebelpaire/selinko/test_nerves_nfc/_build/rpi3/dev/nerves/system/staging/usr/include/sys/types.h:201:1: note: in expansion of macro '__u_intN_t'
 __u_intN_t (16, __HI__);
 ^
  CCLD   nfc-emulate-forum-tag4
nfc-emulate-forum-tag4.o: In function `nfcforum_tag4_io':
nfc-emulate-forum-tag4.c:(.text+0x34): undefined reference to `print_hex'
nfc-emulate-forum-tag4.c:(.text+0x2fc): undefined reference to `print_hex'
collect2: error: ld returned 1 exit status
make[3]: *** [nfc-emulate-forum-tag4] Error 1
make[2]: *** [all-recursive] Error 1
make[1]: *** [all] Error 2
make: *** [libnfc] Error 2
```
