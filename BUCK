include_defs('//BUCKAROO_DEPS')

macos_sources = glob([
  'src/posix/**/*.cpp', 
]) + [
  'src/asm/jump_x86_64_sysv_macho_gas.S', 
  'src/asm/make_x86_64_sysv_macho_gas.S', 
  'src/asm/ontop_x86_64_sysv_macho_gas.S', 
]

cxx_library(
  name = 'context',
  header_namespace = 'boost/context',
  exported_headers = subdir_glob([
    ('include/boost/context', '**/*.hpp'),
    ('include/boost/context', '**/*.ipp'),
  ]),
  srcs = glob([
    'src/*.cpp',
    'src/asm/**/*.cpp',
  ], 
  excludes = [
    'src/unsupported.cpp',
    'src/untested.cpp',
  ]),
  platform_srcs = [
    ('default', glob(['src/posix/**/*.cpp'])),
    ('^macosx.*', macos_sources), 
    ('^linux.*', glob(['src/posix/**/*.cpp'])),
    ('^windows.*', glob(['src/windows/**/*.cpp'])),
  ],
  visibility = [
    'PUBLIC',
  ], 
  deps = BUCKAROO_DEPS,
)
