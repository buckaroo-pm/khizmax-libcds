load('//:subdir_glob.bzl', 'subdir_glob')
load('//:buckaroo_macros.bzl', 'buckaroo_deps')

cxx_library(
  name = 'cds',
  header_namespace = 'cds',
  exported_headers = subdir_glob([
    ('cds', '**/*.h'),
  ]),
  srcs = glob([
    'src/**/*.cpp',
  ]),
  compiler_flags = [
    '-std=c++14',
  ],
  visibility = [
    'PUBLIC',
  ]
)

cxx_test(
  name = 'misc-only',
  deps = [':cds'] + buckaroo_deps(),
  srcs = glob([
   'test/unit/main.cpp',
   'test/unit/misc/*.cpp'
  ]),
  headers = subdir_glob([
    ('test/unit', '**/*.h'),
    ('test/include', '**/*.h')
  ])
)

