## SSH Ramdisk Loader By [@msftguy](https://github.com/msftguy/ssh-rd) modified to help with installing De Rebus Antiquis

### Changes Made By Me
- Added gptfdisk, df, hfs_resize, dd, reboot and sync to the ramdisk  
- Added a shell script to partition the disk and flash [@dora_IOS](https://twitter.com/dora_iOS)'s ramdisk.

### Thanks to:
- [@msftguy](https://github.com/msftguy/ssh-rd) for the original ssh ramdisk tool
- [@xerub](https://twitter.com/xerub) For De Rebus Antiquis
- [@dora_IOS](https://twitter.com/dora_iOS) for the untethered ramdisk

### Building: 
- Submodules (xpwn and syringe)
git submodule init
git submodule update
- OS X: you need libusb and arm-elf-binutils (and maybe arm-elf-gcc?) from macports to build syringe
- Boost: Stripped down boost needed by fuzzy_patcher included in _3rd/boost_1_48_0: run bootstrap.sh/.cmd, then use build-osx.sh or build-win32.cmd to build.
- general building - OS X: cd syringe; make all; cd ../xpwn; make all; cd ../mux_redux; make all; cd ../fuzzy_patcher; make all; cd jsyringeapi; make all; cp *.jnilib ../java/gui/src/res/native/
- general building - Win32: Just set JAVA_HOME to where the JDK is and build the solution.

- Building the Java project:
 Use Eclipse; add stuff from java/_3rd as external JARs.
 On Windows, make sure to use a 32-bit JDK environment to build/debug the java/gui project; since iTunes DLLs are 32bit, and so are the native DLLs that the solution builds.
