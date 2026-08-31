#### --- GENERATED --- ####

libavutil_x86_sources = files(
  'cpu.c',
)

libavutil_x86_x86asm_sources = files(
  'cpuid.asm',
  'crc.asm',
  'fixed_dsp.asm',
  'fixed_dsp_init.c',
  'float_dsp.asm',
  'float_dsp_init.c',
  'imgutils.asm',
  'imgutils_init.c',
  'lls.asm',
  'lls_init.c',
  'tx_float.asm',
  'tx_float_init.c',
  'aes.asm',
  'aes_init.c',
)

libavutil_x86_x86asm_optional_sources = {
  'pixelutils' : files('pixelutils.asm'),
}

# libavutil_x86_emms_sources = files(
#   'emms.asm', # MANUAL
# )

#### --- END GENERATED --- ####

if conf.get('aesni_external', 0) == 1
  libavutil_x86_x86asm_sources += files(
    'aes_init.c',
    'aes.asm',
  )
endif

if conf.get('mmx_inline', 0) == 0 and conf.get('mmx_empty', 0) == 0
  libavutil_slib_optional_sources += {
    'mmx_external': files('emms.asm')
  }
endif
