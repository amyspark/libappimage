test_desktop_integration_sources = files(
    'TestIntegrationManager.cpp',
    'integrator/TestDesktopIntegration.cpp',
    'integrator/TestDesktopEntryEditor.cpp',
)

if thumbnailer.enabled()
    test_desktop_integration_sources += files(
        'TestThumbnailer.cpp'
    )
endif

test_desktop_integration_deps = [
    core,
    test_dep,
    appimage_utils,
    appimage_desktop_integration,
    temporarydirectory_dep,
    libappimage,
    libappimage_shared_dep,
    libsquashfuse,
    libarchive,
    xz,
    libzlib,
    xdg_utils_desktop_entry,
    xdg_utils_base_dir,
    libglib,
    gtest,
    librsvg,
    libcairo,
]

test_desktop_integration = executable(
    'test_desktop_integration',
    test_desktop_integration_sources,
    dependencies: test_desktop_integration_deps,
)

test('TestDesktopIntegration', test_desktop_integration)
