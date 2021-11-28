# libpng-android-build

### Cross-compiles libpng library for Android

This script cross-compiles **libpng library** for Android (armeabi-v7a, arm64-v8a, x86, x86-64) using **Android NDK** and **autoconf**, as shown in [Use the NDK with other build systems](https://developer.android.com/ndk/guides/other_build_systems#autoconf).

> This script has been tested on Debian GNU/Linux 10 (buster) x86_64 with Android NDK r22b (22.1.7171670).

> This script download libpng source code from libpng official sourceforge repository (https://download.sourceforge.net/libpng/)

### Dependencies:

- Android NDK r22+
- curl
- make

### Android Arch Supported:

- arm (armeabi-v7a)
- arm64 (arm64-v8a)
- x86
- x86-64

### Usage examples:

Build **libpng-1.6.37** static and shared libs, for android-21, all supported architectures

```
build_libpng
```

Build **libpng-1.1.10** static and shared libs, for android-21, armeabi-v7a

```
build_libpng --ndk-dir /path/to/android-ndk --android-abi arm --libpng-version 1.1.10
```

Build **libpng-1.6.37** static libs, for android-24, arm64-v8a with zlib support

```
build_libpng --with-zlib /zlib/install/prefix  --android-abi arm64 --android-api-level 24 --static-only
```

> If the script is invoked with no arguments, by default **libpng-1.6.37** static and shared libraries are compiled for android-21 (armeabi-v7a, arm64-v8a, x86, x86-64) using the **Android NDK** path provided by **ANDROID_NDK** environment variable.

### TODO:

- Improve message logging, log all events (err, std) in `build.log` file.
- Implement clean callback on error.
