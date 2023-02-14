xdg_basedir_files = files('xdg-basedir.c')

xdg_basedir_lib = static_library(
    'xdg-basedir',
    xdg_basedir_files,
    pic: true,
)

xdg_basedir = declare_dependency(
    link_with: xdg_basedir_lib,
    include_directories: include_directories('.'),
)
