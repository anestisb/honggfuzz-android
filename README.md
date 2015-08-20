honggfuzz android
=================

**!!! Project is deprecated. Use [upstream mirror](https://github.com/anestisb/honggfuzz) instead.**

An Android port of the [honggfuzz](https://code.google.com/p/honggfuzz/) general purpose fuzzer tool.

## General Info

POSIX/SIGNAL architecture has been chosen in order to be compatible with most of the Android ecosystems. PTRACE arch interfaces probably should also work, although they require lot of crafting (feel free to tweak & test them).


Pay extra attention to the number of parallel tasks based on your hardware & fuzzing target.

## ChangeLog

### version 3.1 (17 July 2014)
* Add support for fuzz mangle area offsets relative to file begin pos for internal data generator
* Add support for `--<arg>=___FILE___` type of arguments in fuzz target

### version 3.0 (14 July 2014)
* Initial port from original repo
* Edits in arch-posix.c to support Android NDK builds

## Building

* Install Android NDK from official [source](https://developer.android.com/tools/sdk/ndk/index.html) (prefer latest version).
* Tweak system path to include NDK root, `build/tools` & `prebuilt/<target>/bin`
* If compiling for devices < API 16 (4.1 JellyBean), disable PIE in `jni/Android.mk:TARGET_IS_PIE`
* Invoke ndk-build in repo root path
* adb push libs/armeabi/honggfuzz to your device
* Have fun :)


Two sample ARM EABI5 executables are included in the bin directory for convenience.

* `MD5 (bin/honggfuzz_PIE) = c571be57dc2d94d3eefe058faaf313da`
* `MD5 (bin/honggfuzz_noPIE) = 13fba34bbad32a2bfd13af84f835eb84`

## License
```
   honggfuzz Android port
   -----------------------------------------

   Author:        Robert Swiecki <swiecki@google.com>
   Modifications: Anestis Bechtsoudis <anestis@census-labs.com>

   Original:      Copyright 2010 by Google Inc. All Rights Reserved.
   Modifications: Copyright 2014 by Census SA. All Rights Reserved.

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
