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

libappimage_private_deps = [
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
    libgio,
    libzlib,
]

if desktop_integration.enabled()
    libappimage_private_deps += appimage_desktop_integration
endif

libappimage_public_deps = [
    libappimage_shared_dep,
    libcairo,
    librsvg
]

libappimage_deps = libappimage_private_deps + libappimage_public_deps
libappimage_incs = libappimage_include_directories + include_directories('.')

libappimage_static = static_library(
    'appimage_static',
    libappimage_sources,
    pic: true,
    c_args: libappimage_module_flags,
    cpp_args: libappimage_module_flags,
    include_directories: libappimage_incs,
    dependencies: libappimage_deps,
)

libappimage_legacy_sources = files(
    'libappimage_legacy.cpp',
)

libappimage_lib = shared_library(
    'appimage',
    libappimage_sources,
    libappimage_legacy_sources,
    c_args: libappimage_module_flags,
    cpp_args: libappimage_module_flags,
    include_directories: libappimage_incs,
    dependencies: libappimage_deps,
    install: true,
)

libappimage = declare_dependency(
    link_with: libappimage_lib,
    dependencies: libappimage_public_deps,
    include_directories: libappimage_incs,
)

# todo: implement cmake export
