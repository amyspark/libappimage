libappimage_shared_files = files(
    'elf.c',
    'hexlify.c',
    'digest.c',
)

libappimage_shared = static_library(
    'appimage_shared',
    libappimage_shared_files,
    include_directories: libappimage_include_directories,
    dependencies: libappimage_hashlib_dep,
    install: true,
)

libappimage_shared_dep = declare_dependency(
    link_with: libappimage_shared,
    include_directories: libappimage_include_directories,
    dependencies: libappimage_hashlib_dep,
)

# TODO: implement cmake export module
