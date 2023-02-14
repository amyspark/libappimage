project('libappimage', 'c', 'cpp',
  version : '1.0.3',
  default_options : ['warning_level=3', 'c_std=c99', 'cpp_std=c++17'])

cxx = meson.get_compiler('cpp')

desktop_integration = get_option('desktop_integration')

libarchive = dependency('libarchive')
libsquashfuse = dependency('squashfuse')
libglib = dependency('glib-2.0')
libgobject = dependency('gobject-2.0')

gtest = dependency('gtest_main', disabler: true)

subdir('src')
subdir('tests')
