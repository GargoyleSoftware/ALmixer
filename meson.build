project('libopenvr_api', 'c', 'cpp',
  default_options : [
      ])

cc = meson.get_compiler('cpp')

src = [
  'src/ALmixer_AndroidExtensions.c',
  'src/ALmixer.c',
  'src/CircularQueue.c',
  'src/LinkedList.c',
  'src/tErrorLib.c',

  'src/StandAlone/SimpleMutex.c',
  'src/StandAlone/SimpleThreadPosix.c',
  'src/StandAlone/SimpleThreadWindows.c',

  'src/StandAlone/SDL/src/file/ALmixer_RWops.c',
  'src/StandAlone/SDL/src/stdlib/ALmixer_getenv.c',
  'src/StandAlone/SDL/src/stdlib/ALmixer_iconv.c',
  'src/StandAlone/SDL/src/stdlib/ALmixer_malloc.c',
  'src/StandAlone/SDL/src/stdlib/ALmixer_stdlib.c',
  'src/StandAlone/SDL/src/stdlib/ALmixer_string.c',

  #'src/StandAlone/SoundDecoder/coreaudio.c',
  # 'src/StandAlone/SoundDecoder/OggTremor.c',
  'src/StandAlone/SoundDecoder/OggVorbis.c',
  #'src/StandAlone/SoundDecoder/OpenSLES_Android.c',
  'src/StandAlone/SoundDecoder/SoundDecoder.c',
  # 'src/StandAlone/SoundDecoder/WindowsMediaFoundation.cpp',
  # 'src/StandAlone/SoundDecoder/WindowsMediaFoundation_IMFByteStreamRWops.cpp',
  # 'src/StandAlone/SoundDecoder/WindowsMediaFoundationProxy.c',

  #'src/StandAlone/SoundDecoder/LGPL/mpg123.c',
  'src/StandAlone/SoundDecoder/LGPL/SDL_sound_minimal.c',
  'src/StandAlone/SoundDecoder/LGPL/wav.c',
]

inc = include_directories(
  'include',
  'src',
  'src/StandAlone/SoundDecoder',
  'src/StandAlone/SDL/include',
  'src/StandAlone/SDL/src',
  'src/StandAlone/SDL/src/core/android',
  'src/StandAlone/SDL/src/core/windows',
  'src/StandAlone/SDL/src/file/cocoa',
)

vorbis_dep = dependency('vorbis', method : 'pkg-config')

libALmixer = library('ALmixer', src,
  link_with: [

  ],
  dependencies: [
    dependency('openal'),
    cc.find_library('pthread'),
    dependency('vorbis'),
    dependency('vorbisfile'),
    dependency('ogg'),
  ],

  include_directories: inc,
  c_args : [
    '-DSOUND_SUPPORTS_WAV',
    '-DSOUND_SUPPORTS_OGG',
    ]
  )

libALmixer_dep = declare_dependency(include_directories: inc,
  link_with: libALmixer)

