#### --- GENERATED --- ####

tests_checkasm_sources = files(
  'ext/src/arm/cpu.c',
  'ext/src/checkasm.c',
  'ext/src/cpu.c',
  'ext/src/function.c',
  'ext/src/perf.c',
  'ext/src/perf/arm.c',
  'ext/src/perf/linux.c',
  'ext/src/perf/macos_kperf.c',
  'ext/src/riscv/cpu.c',
  'ext/src/signal.c',
  'ext/src/stackguard.c',
  'ext/src/stats.c',
  'ext/src/utils.c',
  'ext/src/x86/cpu.c',
)

tests_checkasm_optional_sources = {
  'aarch64' : files('ext/src/arm/checkasm_64.S'),
  'arm' : files('ext/src/arm/checkasm_32.S'),
  'loongarch' : files('ext/src/loongarch/checkasm.S'), # MANUAL
  'rv' : files('ext/src/riscv/callcheck.S'),
  'x86asm' : files('ext/src/x86/checkasm.asm'), # MANUAL
}

tests_checkasm_avcodec_optional_sources = {
  'aac_decoder' : files('aacpsdsp.c','sbrdsp.c'),
  'aac_encoder' : files('aacencdsp.c'),
  'ac3dsp' : files('ac3dsp.c'),
  'alac_decoder' : files('alacdsp.c'),
  'apv_decoder' : files('apv_dsp.c'),
  'audiodsp' : files('audiodsp.c'),
  'blockdsp' : files('blockdsp.c'),
  'bswapdsp' : files('bswapdsp.c'),
  'cavs_decoder' : files('cavsdsp.c'),
  'dca_decoder' : files('dcadsp.c','synth_filter.c'),
  'dirac_decoder' : files('diracdsp.c'),
  'exr_decoder' : files('exrdsp.c'),
  'fdctdsp' : files('fdctdsp.c'),
  'flac_decoder' : files('flacdsp.c'),
  'fmtconvert' : files('fmtconvert.c'),
  'g722dsp' : files('g722dsp.c'),
  'h263dsp' : files('h263dsp.c'),
  'h264chroma' : files('h264chroma.c'),
  'h264dsp' : files('h264dsp.c'),
  'h264pred' : files('h264pred.c'),
  'h264qpel' : files('h264qpel.c'),
  'hevc_decoder' : files('hevc_add_res.c','hevc_deblock.c','hevc_dequant.c','hevc_idct.c','hevc_pel.c','hevc_pred.c','hevc_sao.c'),
  'hpeldsp' : files('hpeldsp.c'),
  'huffyuvdsp' : files('huffyuvdsp.c'),
  'huffyuvencdsp' : files('huffyuvencdsp.c'),
  'idctdsp' : files('idctdsp.c'),
  'jpeg2000_decoder' : files('jpeg2000dsp.c'),
  'llauddsp' : files('llauddsp.c'),
  'llviddsp' : files('llviddsp.c'),
  'llvidencdsp' : files('llvidencdsp.c'),
  'lpc' : files('lpc.c'),
  'me_cmp' : files('motion.c'),
  'mpeg4_decoder' : files('mpeg4videodsp.c'),
  'mpegvideo' : files('mpegvideo_unquantize.c'),
  'mpegvideoencdsp' : files('mpegvideoencdsp.c'),
  'opus_decoder' : files('opusdsp.c'),
  'pixblockdsp' : files('pixblockdsp.c'),
  'png_decoder' : files('png.c'),
  'qpeldsp' : files('qpeldsp.c'),
  'rv34dsp' : files('rv34dsp.c'),
  'rv40_decoder' : files('rv40dsp.c'),
  'sbc_encoder' : files('sbcdsp.c'),
  'snow_decoder' : files('snowdsp.c'),
  'svq1_encoder' : files('svq1enc.c'),
  'tak_decoder' : files('takdsp.c'),
  'utvideo_decoder' : files('utvideodsp.c'),
  'v210_decoder' : files('v210dec.c'),
  'v210_encoder' : files('v210enc.c'),
  'vc1dsp' : files('vc1dsp.c'),
  'videodsp' : files('videodsp.c'),
  'vorbis_decoder' : files('vorbisdsp.c'),
  'vp3dsp' : files('vp3dsp.c'),
  'vp6_decoder' : files('vp6dsp.c'),
  'vp8dsp' : files('vp8dsp.c'),
  'vp9_decoder' : files('vp9dsp.c'),
  'vvc_decoder' : files('vvc_alf.c','vvc_mc.c','vvc_sao.c'),
}

tests_checkasm_avfilter_optional_sources = {
  'afir_filter' : files('af_afir.c'),
  'blackdetect_filter' : files('vf_blackdetect.c'),
  'blend_filter' : files('vf_blend.c'),
  'bwdif_filter' : files('vf_bwdif.c'),
  'colordetect_filter' : files('vf_colordetect.c'),
  'colorspace_filter' : files('vf_colorspace.c'),
  'eq_filter' : files('vf_eq.c'),
  'fspp_filter' : files('vf_fspp.c'),
  'gblur_filter' : files('vf_gblur.c'),
  'hflip_filter' : files('vf_hflip.c'),
  'idet_filter' : files('vf_idet.c'),
  'nlmeans_filter' : files('vf_nlmeans.c'),
  'pp7_filter' : files('vf_pp7.c'),
  'scene_sad' : files('scene_sad.c'),
  'sobel_filter' : files('vf_convolution.c'),
  'threshold_filter' : files('vf_threshold.c'),
}

tests_checkasm_avutil_sources = files(
  'aes.c',
  'av_tx.c',
  # FIXME upstream: the call to av_mallocz yields a truncated (void* to
  # int32_t) pointer because the function is not properly declared on MSVC.
  # This causes the CRC test to fail.
  # Needs a simple #include <libavutil/mem.h> to work. -Amy
  'meson/crc.c',
  'fixed_dsp.c',
  'float_dsp.c',
  'lls.c',
)

tests_checkasm_avutil_optional_sources = {
  'pixelutils' : files('pixelutils.c'),
}

tests_checkasm_swscale_sources = files(
  'sw_gbrp.c',
  'sw_ops.c',
  'sw_range_convert.c',
  'sw_rgb.c',
  'sw_scale.c',
  'sw_xyz2rgb.c',
  'sw_yuv2rgb.c',
  'sw_yuv2yuv.c',
)

#### --- END GENERATED --- ####

if conf.get('avcodec', 0) == 1
  foreach k, v: tests_checkasm_avcodec_optional_sources
    tests_checkasm_optional_sources += {
      k: tests_checkasm_optional_sources.get(k, []) + v
    }
  endforeach
endif

if conf.get('avfilter', 0) == 1
  foreach k, v: tests_checkasm_avfilter_optional_sources
    tests_checkasm_optional_sources += {
      k: tests_checkasm_optional_sources.get(k, []) + v
    }
  endforeach
endif

if conf.get('avutil', 0) == 1
  foreach k, v: tests_checkasm_avutil_optional_sources
    tests_checkasm_optional_sources += {
      k: tests_checkasm_optional_sources.get(k, []) + v
    }
  endforeach
  tests_checkasm_sources += tests_checkasm_avutil_sources
endif

if conf.get('swscale', 0) == 1
  tests_checkasm_sources += tests_checkasm_swscale_sources
endif

foreach comp_name, comp_sources : tests_checkasm_optional_sources
  comp_neg = comp_name.startswith('!')
  comp_name = comp_name.strip('!')
  if conf.get(comp_name, 0) == (comp_neg ? 0 : 1)
    tests_checkasm_sources += comp_sources
  endif
endforeach

if conf.get('checkasm', 0) == 1
  checkasm_lib = static_library('checkasm-static',
    tests_checkasm_sources,
    # Expose checkasm_config_header_generated.h to checkasm tests as well, as it
    # modifies the behavior of include/checkasm/header_config.h
    c_args: c_args + ['-DCHECKASM_HAVE_HEADER_GENERATED_H'],
    # Prepend the local checkasm include path before any potential external
    # (possibly outdated) version of libcheckasm.
    include_directories: [include_directories('ext/src', 'ext/include'), common_incs],
    implicit_include_directories : false,
    install: false,
  )

  checkasm_deps = common_deps + optional_deps

  foreach built_lib: built_libs
    checkasm_deps += [get_variable('lib@0@_static_dep'.format(built_lib[0]))]
  endforeach

  checkasm = executable('checkasm',
    files('checkasm.c'),
    objects: checkasm_lib.extract_all_objects(recursive: true),
    link_language: 'c',
    # Expose checkasm_config_generated.h/asm only to checkasm itself.
    c_args: c_args + ['-DCHECKASM_HAVE_HEADER_GENERATED_H', '-DCHECKASM_HAVE_GENERATED_H', '-Umain'],
    # Prepend the local checkasm include path before any potential external
    # (possibly outdated) version of libcheckasm.
    include_directories: [include_directories('ext/src', 'ext/include'), common_incs],
    dependencies: checkasm_deps,
    pie: get_option('b_pie') and (conf.get('pic') == 1),
    override_options: global_overrides,
    install: false,
  )

  fate_checkasm_tests = [
    'aacencdsp',
    'aacpsdsp',
    'ac3dsp',
    'aes',
    'af_afir',
    'alacdsp',
    'apv_dsp',
    'audiodsp',
    'av_tx',
    'blockdsp',
    'bswapdsp',
    'cavsdsp',
    'crc',
    'dcadsp',
    'diracdsp',
    'exrdsp',
    'fdctdsp',
    'fixed_dsp',
    'flacdsp',
    'float_dsp',
    'fmtconvert',
    'g722dsp',
    'h263dsp',
    'h264chroma',
    'h264dsp',
    'h264pred',
    'h264qpel',
    'hevc_add_res',
    'hevc_deblock',
    'hevc_dequant',
    'hevc_idct',
    'hevc_pel',
    'hevc_pred',
    'hevc_sao',
    'hpeldsp',
    'huffyuvdsp',
    'huffyuvencdsp',
    'idctdsp',
    'jpeg2000dsp',
    'llauddsp',
    'lls',
    'llviddsp',
    'llvidencdsp',
    'lpc',
    'motion',
    'mpeg4videodsp',
    'mpegvideo_unquantize',
    'mpegvideoencdsp',
    'opusdsp',
    'pixblockdsp',
    'pixelutils',
    'png',
    'qpeldsp',
    'sbrdsp',
    'rv34dsp',
    'rv40dsp',
    'sbcdsp',
    'scene_sad',
    'snowdsp',
    'svq1enc',
    'synth_filter',
    'sw_gbrp',
    'sw_ops',
    'sw_range_convert',
    'sw_rgb',
    'sw_scale',
    'sw_xyz2rgb',
    'sw_yuv2rgb',
    'sw_yuv2yuv',
    'takdsp',
    'utvideodsp',
    'v210dec',
    'v210enc',
    'vc1dsp',
    'vf_blackdetect',
    'vf_blend',
    'vf_bwdif',
    'vf_colordetect',
    'vf_colorspace',
    'vf_eq',
    'vf_fspp',
    'vf_gblur',
    'vf_hflip',
    'vf_idet',
    'vf_nlmeans',
    'vf_pp7',
    'vf_threshold',
    'vf_sobel',
    'videodsp',
    'vorbisdsp',
    'vp3dsp',
    'vp6dsp',
    'vp8dsp',
    'vp9dsp',
    'vvc_alf',
    'vvc_mc',
    'vvc_sao',
  ]
endif
