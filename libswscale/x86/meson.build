#### --- GENERATED --- ####

libswscale_x86_sources = files(
  'rgb2rgb.c',
  'swscale.c',
  'yuv2rgb.c',
)

libswscale_x86_optional_sources = {
  'mmxext_inline' : files('hscale_fast_bilinear_simd.c'),
  'xmm_clobber_test' : files('w64xmmtest.c'),
}

libswscale_x86_x86asm_sources = files(
  'input.asm',
  'output.asm',
  'scale.asm',
  'scale_avx2.asm',
  'range_convert.asm',
  'rgb_2_rgb.asm',
  'yuv_2_rgb.asm',
  'yuv2yuvX.asm',
)

libswscale_x86_x86asm_optional_sources = {
  # 'unstable' : files('ops_common.asm','ops_int.asm','ops_float.asm','ops.c'), # MANUAL
}

# libswscale_x86_emms_sources = files(
#   'emms.asm', # MANUAL
# )

#### --- END GENERATED --- ####

if conf.get('mmx_inline', 0) == 0 and conf.get('mmx_empty', 0) == 0
  libswscale_shlib_optional_sources += {
    'mmx_external': files('emms.asm')
  }
endif

if conf.get('x86_64', 0) == 1
  uops_macros_gen_asm = cc.preprocess(
    'uops_macros.asm.h',
    include_directories: include_directories('..'),
    output: 'uops_macros.gen',
  )

  # FIXME upstream: Meson, for some reason, preprocesses to an anonymous location?? -Amy
  # https://github.com/mesonbuild/meson/issues/15806
  uops_macros_gen_asm_final = custom_target(
    'uops_macros.gen.asm',
    command: [python3, '-c', 'import sys; import shutil; shutil.copy(sys.argv[1], sys.argv[2])', '@INPUT@', '@OUTPUT@'],
    depends: uops_macros_gen_asm,
    input: uops_macros_gen_asm[0],
    output: 'uops_macros.gen.asm',
  )

  # FIXME upstream: Meson recognises files only by extension, and since the
  # file above is a header, Nasm < 3.01 will trigger the usual "assertion
  # cv8_state.source_files != NULL failed".
  # So the only way is to trigger a genfile dependency and then build.
  copier = generator(python3,
    output : '@PLAINNAME@',
    arguments : [
      '-c', 'import sys; import shutil; shutil.copy(sys.argv[1], sys.argv[2])', '@INPUT@', '@OUTPUT@'
    ],
    depends: uops_macros_gen_asm_final,
  )

  genfiles = copier.process(files(
    'ops_common.asm', 'ops_int.asm','ops_float.asm',
  ))

  libswscale_x86_x86asm_optional_sources += {
    'unstable' : [files('ops.c'), genfiles],
  }
endif
