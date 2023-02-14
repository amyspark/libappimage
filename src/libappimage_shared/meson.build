libappimage_shared_files = files(
    'elf.c',
    'hexlify.c',
    'digest.c',
)

appimage_shared = static_library(
    'appimage_shared',
    libappimage_shared_files,
    include_directories: libappimage_include_directories,
    dependencies: libappimage_hashlib,
    install: true,
)

libappimage_shared = declare_dependency(
    link_with: appimage_shared,
    include_directories: libappimage_include_directories,
    dependencies: libappimage_hashlib,
)

# TODO: implement cmake export module
