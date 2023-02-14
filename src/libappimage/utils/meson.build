appimage_utils_sources = files(
    'MagicBytesChecker.cpp',
    'ElfFile.cpp',
    'hashlib.cpp',
    'UrlEncoder.cpp',
    'IconHandle.cpp',
    'Logger.cpp',
    'path_utils.cpp',
    'resources_extractor/ResourcesExtractor.cpp',
    'resources_extractor/PayloadEntriesCache.cpp',
    'StringSanitizer.cpp',
    'IconHandleCairoRsvg.cpp',
)

appimage_utils = declare_dependency(
    sources: appimage_utils_sources,
    dependencies: [boost, xdg_utils_desktop_entry, xdg_utils_base_dir, libcairo, librsvg],
    link_with: [libappimage_hashlib],
)
