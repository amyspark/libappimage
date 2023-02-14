appimage_desktop_integration_sources = files(
    'IntegrationManager.cpp',
    'integrator/Integrator.cpp',
    'integrator/DesktopEntryEditor.cpp',
)

if get_option('thumbnailer').enabled()
    appimage_desktop_integration_sources += files(
        'Thumbnailer.cpp'
    )
endif

appimage_desktop_integration = declare_dependency(
    sources: appimage_desktop_integration_sources,
    dependencies: [libappimage_hashlib_dep, boost, libarchive, libsquashfuse, libglib, xdg_utils_desktop_entry, xdg_utils_base_dir],
    compile_args: libappimage_module_flags,
    include_directories: libappimage_include_directories,
)
