package(default_visibility = ["//visibility:public"])

cc_library(
    name="ALmixer",
    hdrs = [
        "src/CircularQueue.h",
        "src/tErrorLib.h",
        "src/ALmixer_AndroidExtensions.h",
        "src/StandAlone/SimpleThread.h",
        "src/StandAlone/SDL/include/ALmixer_config_pandora.h",
        "src/StandAlone/SDL/include/ALmixer_config_macosx.h",
        "src/StandAlone/SDL/include/ALmixer_config_android.h",
        "src/StandAlone/SDL/include/ALmixer_endian.h",
        "src/StandAlone/SDL/include/ALmixer_begin_code.h",
        "src/StandAlone/SDL/include/ALmixer_system.h",
        "src/StandAlone/SDL/include/ALmixer_config_wiz.h",
        "src/StandAlone/SDL/include/ALmixer_stdinc.h",
        "src/StandAlone/SDL/include/ALmixer_config_minimal.h",
        "src/StandAlone/SDL/include/ALmixer_config_winrt.h",
        "src/StandAlone/SDL/include/ALmixer_config_psp.h",
        "src/StandAlone/SDL/include/ALmixer_config_iphoneos.h",
        "src/StandAlone/SDL/include/ALmixer_config_windows.h",
        "src/StandAlone/SDL/include/ALmixer_close_code.h",
        "src/StandAlone/SDL/include/ALmixer_platform.h",
        "src/StandAlone/SDL/include/ALmixer_config.h",
        "src/StandAlone/SDL/src/file/cocoa/ALmixer_rwopsbundlesupport.h",
        "src/StandAlone/SDL/src/ALmixer_internal.h",
        "src/StandAlone/SDL/src/core/windows/ALmixer_windows.h",
        "src/StandAlone/SDL/src/core/android/ALmixer_android.h",
        "src/StandAlone/SimpleMutex.h",
        "src/StandAlone/SoundDecoder/SoundDecoder.h",
        "src/StandAlone/SoundDecoder/SoundDecoder_Internal.h",
        "src/LinkedList.h",

        "include/ALmixer.h",
        "include/ALmixer_PlatformExtensions.h",
        "include/ALmixer_RWops.h",
        ],
    includes = [
        'include',
        'src',
        "src/StandAlone/SDL/include",
        "src/StandAlone/SoundDecoder",
    ],
    srcs = [
      'src/ALmixer_AndroidExtensions.c',
      'src/ALmixer.c',
      'src/CircularQueue.c',
      'src/LinkedList.c',
      'src/tErrorLib.c',

      'src/StandAlone/SimpleMutex.c',

      'src/StandAlone/SDL/src/file/ALmixer_RWops.c',
      'src/StandAlone/SDL/src/stdlib/ALmixer_getenv.c',
      'src/StandAlone/SDL/src/stdlib/ALmixer_iconv.c',
      'src/StandAlone/SDL/src/stdlib/ALmixer_malloc.c',
      'src/StandAlone/SDL/src/stdlib/ALmixer_stdlib.c',
      'src/StandAlone/SDL/src/stdlib/ALmixer_string.c',

      'src/StandAlone/SoundDecoder/SoundDecoder.c',
      # 'src/StandAlone/SoundDecoder/coreaudio.c',
      # 'src/StandAlone/SoundDecoder/OggTremor.c',
      # 'src/StandAlone/SoundDecoder/OpenSLES_Android.c',

      #'src/StandAlone/SoundDecoder/LGPL/mpg123.c',
      'src/StandAlone/SoundDecoder/LGPL/SDL_sound_minimal.c',
      'src/StandAlone/SoundDecoder/LGPL/wav.c',
    ] + select({
        "//platforms:win32": [
            'src/StandAlone/SoundDecoder/WindowsMediaFoundation.cpp',
            'src/StandAlone/SoundDecoder/WindowsMediaFoundation_IMFByteStreamRWops.cpp',
            'src/StandAlone/SoundDecoder/WindowsMediaFoundationProxy.c',
            'src/StandAlone/SimpleThreadWindows.c',
            ],
        "//conditions:default": [
            'src/StandAlone/SoundDecoder/OggVorbis.c',
            'src/StandAlone/SimpleThreadPosix.c',
            ]}),

    deps = [
        ] + select({
        "//platforms:win32": [
            '//3rdparty/mccarthy-bindeps/alsoft' 
            ],
        "//conditions:default": [
            ],
            }),
    copts = select({
        "//platforms:win32": [

        ],
        "//conditions:default": [
            '-lAL',
            '-I/usr/include/AL',]}),
    defines = select({
        "//platforms:win32": [
            '_WIN32',
        ],
        "//conditions:default": [
        ]}))

