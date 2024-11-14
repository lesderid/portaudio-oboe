# PortAudio implementation for Android using Oboe.

## How to use

1. Install Android NDK
2. Build portaudio-oboe

   For example:

    ```
    cmake -S . -B build \
        -DANDROID=1 \
        -DANDROID_ABI=armeabi-v7a \
        -DANDROID_PLATFORM=android-21 \
        -DBUILD_SHARED_LIBS=ON \
        -DCMAKE_INSTALL_PREFIX=$INSTALL_PREFIX \
        -DCMAKE_TOOLCHAIN_FILE=$ANDROID_NDK_HOME/build/cmake/android.toolchain.cmake
    cmake --build build --target install
    ```
3. Add liboboe.so and libportaudio.so to your app

## TODOs

* Testing. This implementation was tested for VoIP calls that use blocking
  streams - for everything else, lots of tests are needed.

## Misc

### Audio Format

If you need to select a specific audio format, you'll have to manually set it in
PaOboe_OpenStream  by modifying the format selection marked with a *FIXME*. I'm
positive that automatic format selection is possible, but simply using
PaUtil_SelectClosestAvailableFormat got me nowhere.

### Buffer sizes

Portaudio often tries to get approximately low buffer sizes, and if you need
specific sizes for your  buffer you should manually modify it (or make a simple
function that can set it). For your convenience,  there is a *FIXME* as a
bookmark.
