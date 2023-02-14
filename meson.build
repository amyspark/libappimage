project('libappimage', 'c', 'cpp',
  version : '1.0.3',
  license: 'MIT',
  meson_version: '>=0.54',
  default_options : ['warning_level=3', 'c_std=gnu99', 'cpp_std=c++17'])

cxx = meson.get_compiler('cpp')

desktop_integration = get_option('desktop_integration')
thumbnailer = get_option('thumbnailer')

# TODO: implement git describe --tags -C $MESON_SOURCE_ROOT
# with fallback to project version and store in -DGIT_COMMIT

libappimage_module_definitions = declare_dependency(
  compile_args: [
    '-D_FILE_OFFSET_BITS=64',
    '-D_LARGEFILE_SOURCE',
    '-DENABLE_BINRELOC',
  ],
  include_directories: include_directories('.')
)

# cmake/dependencies.cmake
xz = dependency('liblzma')
libsquashfuse = dependency('squashfuse')
libarchive = dependency('libarchive')
boost = dependency('boost')
xdg_utils_desktop_entry = dependency('XdgUtils', method : 'cmake', modules: ['XdgUtils::DesktopEntry'], components: ['DesktopEntry'])
xdg_utils_base_dir = dependency('XdgUtils', method : 'cmake', modules: ['XdgUtils::BaseDir'], components: ['BaseDir'])

# cmake/imported_dependencies.cmake.in
# todo: if shared only
libglib = dependency('glib-2.0', version : '>=2.40')
libgobject = dependency('gobject-2.0', version : '>=2.40')
libgio = dependency('gio-2.0', version : '>=2.40')
libzlib = dependency('zlib')
libcairo = dependency('cairo')
librsvg = dependency('librsvg-2.0')

# lib/cmakelists.txt
gtest = dependency('gtest_main', disabler: true)

subdir('src')
subdir('tests')
