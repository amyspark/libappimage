cfg = configuration_data()

cfg.set('LIBAPPIMAGE_VERSION_MAJOR', v_major)
cfg.set('LIBAPPIMAGE_VERSION_MINOR', v_minor)
cfg.set('LIBAPPIMAGE_VERSION_PATCH', v_patch)
cfg.set_quoted('LIBAPPIMAGE_VERSION_SUFFIX', '')
cfg.set_quoted('LIBAPPIMAGE_VERSION', meson.project_version())
if desktop_integration.enabled()
    cfg.set10('LIBAPPIMAGE_DESKTOP_INTEGRATION_ENABLED', true)
endif
if thumbnailer.enabled()
    cfg.set10('LIBAPPIMAGE_THUMBNAILER_ENABLED', true)
endif

config_h = configure_file(
    configuration: cfg,
    output: 'config.h'
)

headers = files(
    'appimage++.h',
    'appimage_shared.h',
    'appimage_legacy.h',
    'appimage.h',
)

install_headers(
    headers + [config_h],
    subdir: 'appimage',
)

headers_core = files(
    'core/PayloadIterator.h',
    'core/PayloadEntryType.h',
    'core/AppImageFormat.h',
    'core/exceptions.h',
    'core/AppImage.h',
)

install_headers(
    headers_core,
    subdir: 'appimage/core',
)

headers_desktop_integration = files(
    'desktop_integration/IntegrationManager.h',
    'desktop_integration/exceptions.h',
)

install_headers(
    headers_desktop_integration,
    subdir: 'appimage/desktop_integration',
)

headers_utils = files(
    'utils/ResourcesExtractor.h',
    'utils/logging.h',
)

install_headers(
    headers_utils,
    subdir: 'appimage/utils',
)

