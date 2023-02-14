subdir('xdg-basedir')
subdir('libappimage_hashlib')
subdir('libappimage_shared')

subdir('libappimage')

if enable_all_targets.enabled()
    pkg = import('pkgconfig')

    pkg.generate(
        libappimage_lib,
        name: meson.project_name(),
        description: 'AppImage management and desktop integration',
        url: 'https://github.com/AppImage/libappimage',
    )
endif
