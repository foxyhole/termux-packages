# Frida-python cross building for Termux

## Requirement
  1. Install frida-core-devkit-12.x.x-android-arm.tar to /data/data/com.termux/files/usr/lib and /data/data/com.termux/files/usr/include .
  2. Create a proper pkgconfig for frida-core-dev like the following
  ```
prefix=/data/data/com.termux/files/usr
exec_prefix=${prefix}
libdir=${exec_prefix}/lib
includedir=${prefix}/include

Name: frida-core
Description: frida-core library
Version: 1.0
Requires:
Libs: -L${libdir} -lfrida-core
Cflags: -I${includedir}/frida-core 
  ```
  3. Create a proper termux crossbuilding environemnt with `script/setup-xxx.sh` or see https://github.com/termux/termux-packages README
  ### footnote
  1. If Android SDK manager is refused to run, see https://stackoverflow.com/questions/47150410/failed-to-run-sdkmanager-list-android-sdk-with-java-9 for the workaround.
  2. if `locale_t` is missing in frida-core.h, you maybe want to include `xlocale.h` 
