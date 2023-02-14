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
    libappimage_module_definitions,
    core,
    appimage_utils,
    libarchive,
    xdg_basedir,
    xdg_utils_desktop_entry,
    xdg_utils_base_dir,
    libappimage_hashlib,
    libsquashfuse,
    xz,
    boost,
    libgio,
    libzlib,
]

if desktop_integration.enabled()
    libappimage_private_deps += appimage_desktop_integration
endif

libappimage_public_deps = [libappimage_shared, libcairo, librsvg]

libappimage_deps = libappimage_private_deps + libappimage_public_deps
libappimage_incs = include_directories('.')

libappimage_static = static_library(
    'appimage_static',
    libappimage_sources,
    pic: true,
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
    include_directories: libappimage_incs,
    dependencies: libappimage_deps,
    version: meson.project_version(),
    soversion: soversion,
    install: true,
)

libappimage = declare_dependency(
    link_with: libappimage_lib,
    dependencies: libappimage_public_deps,
    include_directories: libappimage_incs,
)
