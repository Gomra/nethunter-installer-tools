If you haven't already, build the Android NDK standalone toolchains:
```sh
mkdir ~/build/ndk
mkdir ~/build/toolchain
cd ~/build/ndk
wget http://dl.google.com/android/ndk/android-ndk-r10e-linux-x86_64.bin
chmod +x android-ndk-r10e-linux-x86_64.bin
./android-ndk-r10e-linux-x86_64.bin
cd android-ndk-r10e
build/tools/make-standalone-toolchain.sh --platform=android-21 --toolchain=arm-linux-androideabi-4.9 --install-dir="$HOME/build/toolchain/android-armhf-4.9"
build/tools/make-standalone-toolchain.sh --platform=android-21 --toolchain=aarch64-linux-android-4.9 --install-dir="$HOME/build/toolchain/android-arm64-4.9"
build/tools/make-standalone-toolchain.sh --platform=android-21 --toolchain=x86_64-4.9 --install-dir="$HOME/build/toolchain/android-amd64-4.9"
build/tools/make-standalone-toolchain.sh --platform=android-21 --toolchain=x86-4.9 --install-dir="$HOME/build/toolchain/android-i386-4.9"
```

Use ./android through source, ex.  
`source ./android`

If building for TWRP (/system not mounted):  
`TWRP=1 source ./android`

If building for armhf:  
`ARCH=armhf source ./android`

If building for arm64:  
`ARCH=arm64 source ./android`

If building for amd64:  
`ARCH=amd64 source ./android`

If building for i386:  
`ARCH=i386 source ./android`

You can set optimization levels too:  
`O=3 source android`
