libappimage_hashlib_files = files(
    'md5.c'
)

libappimage_hashlib_inc = include_directories('include')

libappimage_hashlib = static_library(
    'appimage_hashlib',
    libappimage_hashlib_files,
    include_directories: libappimage_hashlib_inc,
    pic: true,
    install: true,
)

libappimage_hashlib_dep = declare_dependency(
    link_with: libappimage_hashlib,
    include_directories: libappimage_hashlib_inc,
)

# TODO: generate cmake output file
