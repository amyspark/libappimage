subdir('xdg-basedir')
subdir('libappimage_hashlib')
subdir('libappimage_shared')

pkg = import('pkgconfig')

subdir('libappimage')
pkg.generate(
    libappimage_lib,
    name: meson.project_name(),
    description: 'AppImage management and desktop integration',
    url: 'https://github.com/AppImage/libappimage',
)
