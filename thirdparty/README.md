# Third party libraries

Please keep categories (`##` level) listed alphabetically and matching their
respective folder names. Use two empty lines to separate categories for
readability.


## brotli

- Upstream: https://github.com/google/brotli
- Version: git (f4153a09f87cbb9c826d8fc12c74642bb2d879ea, 2022)
- License: MIT

Files extracted from upstream source:

- `common/`, `dec/` and `include/` folders
- `LICENSE`


## bullet

- Upstream: https://github.com/bulletphysics/bullet3
- Version: 3.24 (7dee3436e747958e7088dfdcea0e4ae031ce619e, 2022)
- License: zlib

Files extracted from upstream source:

- `src/*` minus `Bullet3*`, `BulletInverseDynamics` and `clew` folders,
  and CMakeLists.txt and premake4.lua files
- `LICENSE.txt`, and `VERSION` as `VERSION.txt`

Includes some patches in the `patches` folder which have been sent upstream.


## certs

- Upstream: Mozilla, via https://github.com/bagder/ca-bundle
- Version: git (7f33e7eb8472dbcf31fdcf50cd216c89a282825d, 2022)
- License: MPL 2.0


## cvtt

- Upstream: https://github.com/elasota/cvtt
- Version: 1.0.0-beta4 (cc8472a04ba110fe999c686d07af40f7839051fd, 2018)
- License: MIT

Files extracted from upstream source:

- all .cpp, .h, and .txt files in ConvectionKernels/


## embree

- Upstream: https://github.com/embree/embree
- Version: 3.13.0 (7c53133eb21424f7f0ae1e25bf357e358feaf6ab, 2021)
- License: Apache 2.0

Files extracted from upstream:

- All cpp files listed in `modules/raycast/godot_update_embree.py`
- All header files in the directories listed in `modules/raycast/godot_update_embree.py`

The `modules/raycast/godot_update_embree.py` script can be used to pull the
relevant files from the latest Embree release and apply some automatic changes.

Some changes have been made in order to remove exceptions and fix minor build errors.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments. Apply the patches in the `patches/` folder when syncing on newer upstream
commits.


## enet

- Upstream: http://enet.bespin.org
- Version: 1.3.17 (e0e7045b7e056b454b5093cb34df49dc4cee0bee, 2020)
- License: MIT

Files extracted from upstream source:

- all .c files in the main directory (except unix.c win32.c)
- the include/enet/ folder as enet/ (except unix.h win32.h)
- LICENSE file

Important: enet.h, host.c, protocol.c have been slightly modified
to be usable by Godot's socket implementation and allow IPv6 and DTLS.
Apply the patches in the `patches/` folder when syncing on newer upstream
commits.

Three files (godot.cpp, enet/godot.h, enet/godot_ext.h) have been added to provide
enet socket implementation using Godot classes.

It is still possible to build against a system wide ENet but doing so
will limit its functionality to IPv4 only.


## etc2comp

- Upstream: https://github.com/google/etc2comp
- Version: git (9cd0f9cae0f32338943699bb418107db61bb66f2, 2017)
- License: Apache 2.0

Files extracted from upstream source:

- all .cpp and .h files in EtcLib/
- README.md, LICENSE, AUTHORS

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments.


## fonts

- `NotoSans*.woff2`, `NotoNaskhArabicUI_Regular.woff2`:
  * Upstream: https://github.com/googlei18n/noto-fonts
  * Version: 1.06 (2017)
  * License: OFL-1.1
  * Comment: Use UI font variant if available, because it has tight vertical metrics and
    good for UI.
- `Hack_Regular.woff2`:
  * Upstream: https://github.com/source-foundry/Hack
  * Version: 3.003 (2018)
  * License: MIT + Bitstream Vera License
- `DroidSans*.woff2`:
  * Upstream: https://android.googlesource.com/platform/frameworks/base/+/master/data/fonts/
  * Version: ? (pre-2014 commit when DroidSansJapanese.ttf was obsoleted)
  * License: Apache 2.0
- All fonts are converted from the `.ttf` sources using `https://github.com/google/woff2` tool.


## freetype

- Upstream: https://www.freetype.org
- Version: 2.12.1 (e8ebfe988b5f57bfb9a3ecb13c70d9791bce9ecf, 2022)
- License: FreeType License (BSD-like)

Files extracted from upstream source:

- `src/` folder, minus the `dlg` and `tools` subfolders
  * These files can be removed: `.dat`, `.diff`, `.mk`, `.rc`, `README*`
- `include/` folder, minus the `dlg` subfolder
- `LICENSE.TXT` and `docs/FTL.TXT`

Some changes have been made in order to prevent LTO from removing code.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments. Apply the patches in the `patches/` folder when syncing on newer upstream
commits.


## glad

- Upstream: https://github.com/Dav1dde/glad
- Version: 0.1.34 (a5ca31c88a4cc5847ea012629aff3690f261c7c4, 2020)
- License: MIT

The files we package are automatically generated.
See the header of glad.c for instructions on how to generate them for
the GLES version Godot targets.


## jpeg-compressor

- Upstream: https://github.com/richgel999/jpeg-compressor
- Version: 2.00 (aeb7d3b463aa8228b87a28013c15ee50a7e6fcf3, 2020)
- License: Public domain or MIT

Files extracted from upstream source:

- `jpgd*.{c,h}`


## libogg

- Upstream: https://www.xiph.org/ogg
- Version: 1.3.5 (e1774cd77f471443541596e09078e78fdc342e4f, 2021)
- License: BSD-3-Clause

Files extracted from upstream source:

- `src/*.{c,h}`
- `include/ogg/*.h` in `ogg/` (run `configure` to generate `config_types.h`)
- `COPYING`


## libpng

- Upstream: http://libpng.org/pub/png/libpng.html
- Version: 1.6.37 (a40189cf881e9f0db80511c382292a5604c3c3d1, 2019)
- License: libpng/zlib

Files extracted from upstream source:

- all .c and .h files of the main directory, except from
  `example.c` and `pngtest.c`
- the arm/ folder
- `scripts/pnglibconf.h.prebuilt` as `pnglibconf.h`
- `LICENSE`


## libsimplewebm

- Upstream: https://github.com/zaps166/libsimplewebm
- Version: git (fe57fd3cfe6c0af4c6af110b1f84a90cf191d943, 2019)
- License: MIT (main), BSD-3-Clause (libwebm)

This contains libwebm, but the version in use is updated from the one used by libsimplewebm,
and may have *unmarked* alterations from that.

Files extracted from upstream source:

- all the .cpp, .hpp files in the main folder except `example.cpp`
- LICENSE

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments.


## libtheora

- Upstream: https://www.theora.org
- Version: 1.1.1 (2010)
- License: BSD-3-Clause

Files extracted from upstream source:

- all .c, .h in lib/
- all .h files in include/theora/ as theora/
- COPYING and LICENSE

Upstream patches included in the `patches` directory have been applied
on top of the 1.1.1 source (not included in any stable release yet).


## libvorbis

- Upstream: https://www.xiph.org/vorbis
- Version: 1.3.7 (0657aee69dec8508a0011f47f3b69d7538e9d262, 2020)
- License: BSD-3-Clause

Files extracted from upstream source:

- `lib/*` except from: `lookups.pl`, `Makefile.*`
- `include/vorbis/*.h` as `vorbis/`
- `COPYING`


## libvpx

- Upstream: https://chromium.googlesource.com/webm/libvpx/
- Version: 1.6.0 (2016)
- License: BSD-3-Clause

Files extracted from upstream source:

TODO.

Important: File `libvpx/vpx_dsp/x86/vpx_subpixel_8t_intrin_avx2.c` has
Godot-made change marked with `// -- GODOT --` comments.

The files `libvpx/third_party/android/cpu-features.{c,h}` were copied
from the Android NDK r18.


## libwebp

- Upstream: https://chromium.googlesource.com/webm/libwebp/
- Version: 1.2.4 (0d1f12546bd803099a60c070517a552483f3790e, 2022)
- License: BSD-3-Clause

Files extracted from upstream source:

- `src/` and `sharpyuv/` except from: `.am`, `.rc` and `.in` files
- `AUTHORS`, `COPYING`, `PATENTS`


## mbedtls

- Upstream: https://github.com/Mbed-TLS/mbedtls
- Version: 2.18.1 (dd79db10014d85b26d11fe57218431f2e5ede6f2, 2022)
- License: Apache 2.0

File extracted from upstream release tarball:

- All `*.h` from `include/mbedtls/` to `thirdparty/mbedtls/include/mbedtls/` except `config_psa.h` and `psa_util.h`.
- All `*.c` and `*.h` from `library/` to `thirdparty/mbedtls/library/` except those starting with `psa_*`.
- The `LICENSE` file.
- Applied the patch in `patches/1453.diff` (upstream PR:
  https://github.com/ARMmbed/mbedtls/pull/1453).
- Added 2 files `godot_core_mbedtls_platform.c` and `godot_core_mbedtls_config.h`
  providing configuration for light bundling with core.


## minimp3

- Upstream: https://github.com/lieff/minimp3
- Version: git (afb604c06bc8beb145fecd42c0ceb5bda8795144, 2021)
- License: CC0 1.0

Files extracted from upstream repository:

- `minimp3.h`
- `minimp3_ex.h`
- `LICENSE`


## miniupnpc

- Upstream: https://github.com/miniupnp/miniupnp
- Version: 2.2.2 (81029a860baf1f727903e5b85307903b3f40cbc8, 2021)
- License: BSD-3-Clause

Files extracted from upstream source:

- All `*.c` and `*.h` files from `miniupnpc` to `thirdparty/miniupnpc/miniupnpc`
- Remove the following test or sample files:
  `listdevices.c minihttptestserver.c miniupnpcmodule.c upnpc.c upnperrors.* test* wingenminiupnpcstrings.c`
- `LICENSE`

The only modified file is `miniupnpcstrings.h`, which was created for Godot
(it is usually autogenerated by cmake). Bump the version number for miniupnpc in that
file when upgrading.

Note: The following upstream patch has been applied, remove this notice on next update.
https://github.com/miniupnp/miniupnp/commit/3a08dd4b89af2e9effa22a136bac86f2f306fd79


## minizip

- Upstream: https://www.zlib.net
- Version: 1.2.12 (zlib contrib, 2022)
- License: zlib

Files extracted from the upstream source:

- contrib/minizip/{crypt.h,ioapi.{c,h},unzip.{c,h},zip.{c,h}}

Important: Some files have Godot-made changes for use in core/io.
They are marked with `/* GODOT start */` and `/* GODOT end */`
comments and a patch is provided in the `patches` folder.


## misc

Collection of single-file libraries used in Godot components.

- `clipper.{cpp,hpp}`
  * Upstream: https://sourceforge.net/projects/polyclipping
  * Version: 6.4.2 (2017) + Godot changes (added optional exceptions handling)
  * License: BSL-1.0
- `fastlz.{c,h}`
  * Upstream: https://github.com/ariya/FastLZ
  * Version: 0.5.0 (4f20f54d46f5a6dd4fae4def134933369b7602d2, 2020)
  * License: MIT
- `hq2x.{cpp,h}`
  * Upstream: https://github.com/brunexgeek/hqx
  * Version: TBD, file structure differs
  * License: Apache 2.0
- `ifaddrs-android.{cc,h}`
  * Upstream: https://chromium.googlesource.com/external/webrtc/stable/talk/+/master/base/ifaddrs-android.h
  * Version: git (5976650443d68ccfadf1dea24999ee459dd2819d, 2013)
  * License: BSD-3-Clause
- `mikktspace.{c,h}`
  * Upstream: https://archive.blender.org/wiki/index.php/Dev:Shading/Tangent_Space_Normal_Maps/
  * Version: 1.0 (2011)
  * License: zlib
- `open-simplex-noise.{c,h}`
  * Upstream: https://github.com/smcameron/open-simplex-noise-in-c
  * Version: git (826f1dd1724e6fb3ff45f58e48c0fbae864c3403, 2020) + custom changes
  * License: Public Domain or Unlicense
- `pcg.{cpp,h}`
  * Upstream: http://www.pcg-random.org
  * Version: minimal C implementation, http://www.pcg-random.org/download.html
  * License: Apache 2.0
- `smaz.{c,h}`
  * Upstream: https://github.com/antirez/smaz
  * Version: git (2f625846a775501fb69456567409a8b12f10ea25, 2012)
  * License: BSD-3-Clause
  * Modifications: use `const char*` instead of `char*` for input string
- `stb_rect_pack.h`
  * Upstream: https://github.com/nothings/stb
  * Version: 1.01 (af1a5bc352164740c1cc1354942b1c6b72eacb8a, 2021)
  * License: Public Domain or Unlicense or MIT
- `stb_vorbis.c`
  * Upstream: https://github.com/nothings/stb
  * Version: 1.20 (314d0a6f9af5af27e585336eecea333e95c5a2d8, 2020)
  * License: Public Domain or Unlicense or MIT
- `triangulator.{cpp,h}`
  * Upstream: https://github.com/ivanfratric/polypartition (`src/polypartition.cpp`)
  * Version: TBD, class was renamed
  * License: MIT
- `yuv2rgb.h`
  * Upstream: http://wss.co.uk/pinknoise/yuv2rgb/ (to check)
  * Version: ?
  * License: BSD


## nanosvg

- Upstream: https://github.com/memononen/nanosvg
- Version: git (bd16c4e6b2842e1f0286dc374d21f85c659862e5, 2022)
- License: zlib

Files extracted from the upstream source:

- All `.h` files in `src/`
- `LICENSE.txt`

`nanosvg.cc` is a custom file added to configure the build of the header only
library.


## oidn

- Upstream: https://github.com/OpenImageDenoise/oidn
- Version: 1.1.0 (c58c5216db05ceef4cde5a096862f2eeffd14c06, 2019)
- License: Apache 2.0

Files extracted from upstream source:

common/* (except tasking.* and CMakeLists.txt)
core/*
include/OpenImageDenoise/* (except version.h.in)
LICENSE.txt
mkl-dnn/include/*
mkl-dnn/src/* (except CMakeLists.txt)
weights/rtlightmap_hdr.tza
scripts/resource_to_cpp.py

Modified files:
Modifications are marked with `// -- GODOT start --` and `// -- GODOT end --`.
Patch files are provided in `oidn/patches/`.

core/autoencoder.cpp
core/autoencoder.h
core/common.h
core/device.cpp
core/device.h
core/transfer_function.cpp

scripts/resource_to_cpp.py (used in modules/denoise/resource_to_cpp.py)


## opus

- Upstream: https://opus-codec.org
- Version: 1.1.5 (opus) and 0.8 (opusfile) (2017)
- License: BSD-3-Clause

Files extracted from upstream source:

- all .c and .h files in src/ (both opus and opusfile)
- all .h files in include/ (both opus and opusfile) as opus/
- remove unused `opus_demo.c`,
- remove `http.c`, `wincerts.c` and `winerrno.h` (part of
  unused libopusurl)
- celt/ and silk/ subfolders
- COPYING


## pcre2

- Upstream: http://www.pcre.org
- Version: 10.40 (3103b8f20a3b9944b177e812fde29fbfb8b90558, 2022)
- License: BSD-3-Clause

Files extracted from upstream source:

- Files listed in the file NON-AUTOTOOLS-BUILD steps 1-4
- All .h files in src/ apart from pcre2posix.h
- src/pcre2_jit_match.c
- src/pcre2_jit_misc.c
- src/sljit/
- AUTHORS and LICENCE

A sljit patch from upstream was backported to fix macOS < 11.0 compilation
in 10.40, it can be found in the `patches` folder.


## pvrtccompressor

- Upstream: https://bitbucket.org/jthlim/pvrtccompressor (dead link)
  Unofficial backup fork: https://github.com/LibreGamesArchive/PVRTCCompressor
- Version: hg (cf7177748ee0dcdccfe89716dc11a47d2dc81af5, 2015)
- License: BSD-3-Clause

Files extracted from upstream source:

- all .cpp and .h files apart from `main.cpp`
- LICENSE.TXT


## recastnavigation

- Upstream: https://github.com/recastnavigation/recastnavigation
- Version: git (5a870d427e47abd4a8e4ce58a95582ec049434d5, 2022)
- License: zlib

Files extracted from upstream source:

- `Recast/` folder without `CMakeLists.txt`
- License.txt


## rvo2

- Upstream: https://github.com/snape/RVO2-3D
- Version: git (bfc048670a4e85066e86a1f923d8ea92e3add3b2, 2021)
- License: Apache 2.0

Files extracted from upstream source:

- All .cpp and .h files in the `src/` folder except for Export.h, RVO.h, RVOSimulator.cpp and RVOSimulator.h
- LICENSE

Important: Some files have Godot-made changes; so to enrich the features
originally proposed by this library and better integrate this library with
Godot. See the patch in the `patches` folder for details.


## squish

- Upstream: https://sourceforge.net/projects/libsquish
- Version: 1.15 (r104, 2017)
- License: MIT

Files extracted from upstream source:

- all .cpp, .h and .inl files

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments and a patch is provided in the squish/ folder.


## tinyexr

- Upstream: https://github.com/syoyo/tinyexr
- Version: 1.0.1 (67010eae802211202d0797f4df2b809f4ba7442c, 2021)
- License: BSD-3-Clause

Files extracted from upstream source:

- `tinyexr.{cc,h}`

The `tinyexr.cc` file was modified to include `zlib.h` which we provide,
instead of `miniz.h` as an external dependency.


## vhacd

- Upstream: https://github.com/kmammou/v-hacd
- Version: git (b07958e18e01d504e3af80eeaeb9f033226533d7, 2019)
- License: BSD-3-Clause

Files extracted from upstream source:

- From `src/VHACD_Lib/`: `inc`, `public` and `src`
- `LICENSE`

Some downstream changes have been made and are identified by
`// -- GODOT start --` and `// -- GODOT end --` comments.
They can be reapplied using the patches included in the `vhacd`
folder.


## wslay

- Upstream: https://github.com/tatsuhiro-t/wslay
- Version: 1.1.1+git (45d22583b488f79d5a4e598cc7675c191c5ab53f, 2021)
- License: MIT

File extracted from upstream release tarball:

- Run `cmake .` to generate `config.h` and `wslayver.h`.
  Contents might need tweaking for Godot, review diff.
- All `*.c` and `*.h` files from `lib/`
- All `*.h` in `lib/includes/wslay/` as `wslay/`
- `wslay/wslay.h` has a small Godot addition to fix MSVC build.
  See `patches/msvcfix.diff`
- `COPYING`


## xatlas

- Upstream: https://github.com/jpcy/xatlas
- Version: git (16ace528acd2cf1f16a7c0dde99c42c486488dbe, 2022)
- License: MIT

Files extracted from upstream source:

- `source/xatlas/xatlas.{cpp,h}`
- `LICENSE`


## zlib

- Upstream: https://www.zlib.net
- Version: 1.2.12 (2022)
- License: zlib

Files extracted from upstream source:

- all .c and .h files


## zstd

- Upstream: https://github.com/facebook/zstd
- Version: 1.5.2 (e47e674cd09583ff0503f0f6defd6d23d8b718d3, 2022)
- License: BSD-3-Clause

Files extracted from upstream source:

- `lib/{common/,compress/,decompress/,zstd.h,zstd_errors.h}`
- `LICENSE`
