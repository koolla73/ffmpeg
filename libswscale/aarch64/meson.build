#### --- GENERATED --- ####

libswscale_aarch64_sources = files(
  'rgb2rgb.c',
  'swscale.c',
  'swscale_unscaled.c',
)

libswscale_aarch64_neon_sources = files(
  'hscale.S',
  'input.S',
  'output.S',
  'range_convert_neon.S',
  'rgb2rgb_neon.S',
  'swscale_unscaled_neon.S',
  'xyz2rgb_neon.S',
  'yuv2rgb_neon.S',
)

libswscale_aarch64_neon_optional_sources = {
  'unstable' : files('ops.c'),
}

#### --- END GENERATED --- ####

if conf.get('neon', 0) == 1
  ops_asmgen = executable('ops_asmgen',
    files('ops_asmgen.c'),
    include_directories: common_incs,
    native: true,
    install: false
  )

  ops_neon_gen_S = custom_target(
    'ops_neon.gen.S',
    command: [
      ops_asmgen,
      '-ops'
    ],
    capture: true,
    output: 'ops_neon.gen.S'
  )

  ops_neon_gen_c = custom_target(
    'ops_neon.gen.c',
    command: [
      ops_asmgen,
      '-lookup'
    ],
    capture: true,
    output: 'ops_neon.gen.c'
  )

  libswscale_aarch64_neon_optional_sources += {
    'unstable': libswscale_aarch64_neon_optional_sources['unstable'] + [
      ops_neon_gen_S,
      ops_neon_gen_c
    ]
  }
endif
