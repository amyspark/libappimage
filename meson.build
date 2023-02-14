project(
    'libappimage',
    'c',
    'cpp',
    version: '1.0.4',
    license: 'MIT',
    meson_version: '>=0.54',
    default_options: ['warning_level=3', 'c_std=gnu99', 'cpp_std=c++17'],
)

v = meson.project_version().split('.')
v_major = v[0]
v_minor = v[1]
v_patch = v[2]
soversion = '@0@.@1@'.format(v_major, v_minor)

cxx = meson.get_compiler('cpp')

if get_option('buildtype') == 'release'
    add_project_arguments(cxx.get_supported_link_arguments('-Wl,--gc-sections'), language: 'cpp')
endif

desktop_integration = get_option('desktop_integration')
thumbnailer = get_option('thumbnailer')
enable_all_targets = get_option('all')

libappimage_module_definitions = declare_dependency(
    compile_args: [
        '-D_FILE_OFFSET_BITS=64',
        '-D_LARGEFILE_SOURCE',
        '-DENABLE_BINRELOC',
    ],
    include_directories: include_directories('include'),
)

# cmake/dependencies.cmake
xz = dependency('liblzma', required: enable_all_targets)
libsquashfuse = dependency('squashfuse', required: enable_all_targets)
libarchive = dependency('libarchive', required: enable_all_targets)
boost = dependency('boost', required: enable_all_targets)
xdg_utils_desktop_entry = dependency(
    'XdgUtils',
    method: 'cmake',
    modules: ['XdgUtils::DesktopEntry'],
    components: ['DesktopEntry'],
    required: enable_all_targets,
)
xdg_utils_base_dir = dependency(
    'XdgUtils',
    method: 'cmake',
    modules: ['XdgUtils::BaseDir'],
    components: ['BaseDir'],
    required: enable_all_targets,
)

# cmake/imported_dependencies.cmake.in
libglib = dependency(
    'glib-2.0',
    version: '>=2.40',
    required: enable_all_targets,
)
libgobject = dependency(
    'gobject-2.0',
    version: '>=2.40',
    required: enable_all_targets,
)
libgio = dependency('gio-2.0', version: '>=2.40', required: enable_all_targets)
libzlib = dependency('zlib', required: enable_all_targets)
libcairo = dependency('cairo', required: enable_all_targets)
librsvg = dependency('librsvg-2.0', required: enable_all_targets)

# lib/cmakelists.txt
gtest = dependency('gtest_main', disabler: true)

subdir('include')
subdir('src')
subdir('tests')
subdir('cmake')
