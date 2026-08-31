kwargs = {'prefix': '#include "libswscale/version.h"'} + get_version_define_kwargs

libswscale_majorver = cc.get_define('LIBSWSCALE_VERSION_MAJOR', kwargs: kwargs)
minorver = cc.get_define('LIBSWSCALE_VERSION_MINOR', kwargs: kwargs)
microver = cc.get_define('LIBSWSCALE_VERSION_MICRO', kwargs: kwargs)

libswscale_version = f'@libswscale_majorver@.@minorver@.@microver@'

#### --- GENERATED --- ####

libswscale_sources = files(
  'alphablend.c',
  'cms.c',
  'csputils.c',
  'hscale.c',
  'hscale_fast_bilinear.c',
  'filters.c',
  'format.c',
  'framepool.c',
  'gamma.c',
  'graph.c',
  'input.c',
  'lut3d.c',
  'options.c',
  'output.c',
  'rgb2rgb.c',
  'slice.c',
  'swscale.c',
  'swscale_unscaled.c',
  'utils.c',
  'version.c',
  'yuv2rgb.c',
  'vscale.c',
)

libswscale_headers = files(
  'swscale.h',
  'version.h',
  'version_major.h',
)

libswscale_optional_sources = {
  'unstable' : files('ops.c','ops_chain.c','ops_dispatch.c','ops_memcpy.c','ops_optimizer.c','rational64.c','uops.c','uops_backend.c'),
}

libswscale_shlib_sources = files(
  'log2_tab.c',
  'half2float.c',
)

libswscale_tests = [
  ['colorspace', files('tests/colorspace.c')],
  ['floatimg_cmp', files('tests/floatimg_cmp.c')],
  ['pixdesc_query', files('tests/pixdesc_query.c')],
  # ['swscale', files('tests/swscale.c')], # MANUAL
  # ['sws_ops', files('tests/sws_ops.c')], # MANUAL
  # ['sws_ops_aarch64', files('tests/sws_ops_aarch64.c')], # MANUAL
]

#### --- END GENERATED --- ####

libswscale_shlib_optional_sources = {}

# Version file
ver_conf = configuration_data()
ver_conf.set('majorver', libswscale_majorver)
ver_conf.set('minorver', minorver)
ver_conf.set('microver', microver)

install_headers(libswscale_headers, subdir: 'libswscale')

libswscale_ver = configure_file(
  input: 'libswscale.v.in',
  output: 'libswscale.ver',
  configuration: ver_conf,
)

subdir('aarch64')
subdir('arm')
subdir('x86')
subdir('vulkan')

if conf.get('vulkan', 0) == 1
  libswscale_optional_sources += {
    'unstable': libswscale_optional_sources['unstable'] + libswscale_vulkan_sources
  }
endif
