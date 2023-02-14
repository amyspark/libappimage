xdg_basedir_files = files(
    'xdg-basedir.c'
)

xdg_basedir = static_library(
    'xdg-basedir',
    xdg_basedir_files,
    pic: true,
)

xdg_basedir_dep = declare_dependency(
    link_with: xdg_basedir,
    include_directories: include_directories('.')
)
