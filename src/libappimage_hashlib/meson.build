libappimage_hashlib_files = files(
    'md5.c'
)

libappimage_hashlib = static_library(
    'libappimage_hashlib',
    libappimage_hashlib_files,
    name_prefix: '',
    include_directories: meson.current_source_dir() / 'include',
    # again, is this safe? -Amy
    pic: true,
    install: true,
)

# TODO: generate cmake output file
