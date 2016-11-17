# Newlib - C library for embedded systems - for esp-open-rtos.

This is fork of git://sourceware.org/git/newlib-cygwin.git with patches required to support esp-open-rtos. Based on Newlib 2.2.0 for esp-open-rtos https://github.com/projectgus/newlib-xtensa which was a fork of Newlib 2.2.0 for xtensa https://github.com/projectgus/newlib-xtensa.git

## Building

```
cd newlib-cygwin
mkdir build
cd build
../configure --with-newlib --enable-multilib --disable-newlib-io-c99-formats --enable-newlib-supplied-syscalls --enable-target-optspace --program-transform-name="s&^&xtensa-lx106-elf-&" --disable-option-checking --with-target-subdir=xtensa-lx106-elf --target=xtensa-lx106-elf --enable-newlib-nano-malloc --enable-newlib-nano-formatted-io --enable-newlib-reent-small --prefix=/tmp/libc
env CROSS_CFLAGS="-DSIGNAL_PROVIDED -DABORT_PROVIDED" make
make install
```
