cmake = import('cmake')

cmake.write_basic_package_version_file(
    name: meson.project_name(),
    version: meson.project_version(),
    compatibility: 'AnyNewerVersion',
)

cmake_cfg = configuration_data()

cmake_cfg.set('LIBAPPIMAGE_SHARED_ONLY', enable_all_targets.disabled())
cmake_cfg.set('PREFIX', get_option('prefix'))
cmake_cfg.set('VERSION', meson.project_version())
cmake_cfg.set('SOVERSION', soversion)

cmake.configure_package_config_file(
    input: 'libappimageConfig.cmake.in',
    configuration: cmake_cfg,
    name: meson.project_name(),
)

imported_deps_h = configure_file(
    input: 'imported_dependencies.cmake.in',
    output: 'imported_dependencies.cmake',
    configuration: cmake_cfg,
)

targets_h = configure_file(
    input: 'libappimageTargets.meson.in',
    output: 'libappimageTargets.meson',
    configuration: cmake_cfg,
)

targets_cfg_h = configure_file(
    input: 'libappimageTargets-noconfig.meson.in',
    output: 'libappimageTargets-noconfig.meson',
    configuration: cmake_cfg,
)

cmake_files = files(
    'scripts.cmake'
) + [imported_deps_h, targets_h, targets_cfg_h]

install_headers(
    cmake_files, 
    subdir: get_option('libdir') / 'cmake' / meson.project_name()
)
