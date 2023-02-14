libappimage_shared_files = files(
    'digest.c',
    'elf.c',
    'hexlify.c',
)

appimage_deps = [libappimage_module_definitions, libappimage_hashlib]

appimage_shared = static_library(
    'appimage_shared',
    libappimage_shared_files,
    dependencies: appimage_deps,
    install: true,
)

libappimage_shared = declare_dependency(
    link_with: appimage_shared,
    dependencies: appimage_deps,
)

# TODO: implement cmake export module
