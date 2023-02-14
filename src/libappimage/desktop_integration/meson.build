appimage_desktop_integration_sources = files(
    'IntegrationManager.cpp',
    'integrator/Integrator.cpp',
    'integrator/DesktopEntryEditor.cpp',
)

if thumbnailer.enabled()
    appimage_desktop_integration_sources += files(
        'Thumbnailer.cpp'
    )
endif

desktop_integration_include_directories = include_directories('.') 

appimage_desktop_integration = declare_dependency(
    sources: appimage_desktop_integration_sources,
    dependencies: [libappimage_module_definitions, libappimage_hashlib, boost, libarchive, libsquashfuse, libglib, xdg_utils_desktop_entry, xdg_utils_base_dir],
    include_directories: desktop_integration_include_directories,
)
