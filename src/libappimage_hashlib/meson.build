libappimage_hashlib_files = files('md5.c')

libappimage_hashlib_incs = include_directories('include')

appimage_hashlib = static_library(
    'appimage_hashlib',
    libappimage_hashlib_files,
    include_directories: libappimage_hashlib_incs,
    pic: true,
    install: true,
)

libappimage_hashlib = declare_dependency(
    link_with: appimage_hashlib,
    include_directories: libappimage_hashlib_incs,
)

# TODO: generate cmake output file
