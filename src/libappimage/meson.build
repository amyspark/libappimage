subdir('core')
subdir('utils')

# see configure_libappimage_module

libappimage_sources = files(
    'libappimage.c',
    'libappimage.cpp',
)

if desktop_integration.enabled()
    subdir('desktop_integration')
endif

libappimage_deps = [
    core,
    appimage_utils,
    libarchive,
    xdg_basedir_dep,
    xdg_utils_desktop_entry,
    xdg_utils_base_dir, 
    libappimage_hashlib_dep,
    libsquashfuse,
    xz,
    boost,
    libappimage_shared_dep,
    libgio,
    libzlib,
    libcairo,
    librsvg
]

if desktop_integration.enabled()
    libappimage_deps += appimage_desktop_integration
endif

libappimage_static = static_library(
    'appimage_static',
    libappimage_sources,
    pic: true,
    c_args: libappimage_module_flags,
    cpp_args: libappimage_module_flags,
    include_directories: libappimage_include_directories,
    dependencies: libappimage_deps,
)

libappimage_legacy_sources = files(
    'libappimage_legacy.cpp',
)

libappimage = shared_library(
    'appimage',
    libappimage_sources,
    libappimage_legacy_sources,
    c_args: libappimage_module_flags,
    cpp_args: libappimage_module_flags,
    include_directories: libappimage_include_directories,
    dependencies: libappimage_deps,
    install: true,
)

# todo: implement cmake export
