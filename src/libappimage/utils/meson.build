appimage_utils_sources = files(
    'resources_extractor/PayloadEntriesCache.cpp',
    'resources_extractor/ResourcesExtractor.cpp',
    'ElfFile.cpp',
    'IconHandle.cpp',
    'IconHandleCairoRsvg.cpp',
    'Logger.cpp',
    'MagicBytesChecker.cpp',
    'StringSanitizer.cpp',
    'UrlEncoder.cpp',
    'hashlib.cpp',
    'path_utils.cpp',
)

appimage_utils = declare_dependency(
    sources: appimage_utils_sources,
    dependencies: [
        libappimage_hashlib,
        boost,
        xdg_utils_desktop_entry,
        xdg_utils_base_dir,
        libcairo,
        librsvg,
    ],
    include_directories: include_directories('.'),
)
