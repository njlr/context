include_defs('//BUCKAROO_DEPS')

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
    ('^macosx.*', glob(['src/posix/**/*.cpp'])),
    ('^linux.*', glob(['src/posix/**/*.cpp'])),
    ('^windows.*', glob(['src/windows/**/*.cpp'])),
  ],
  visibility = [
    'PUBLIC',
  ], 
  deps = BUCKAROO_DEPS,
)
