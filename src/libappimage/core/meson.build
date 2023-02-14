core_files = files(
    'impl/StreambufType1.cpp',
    'impl/StreambufType2.cpp',
    'impl/TraversalType1.cpp',
    'impl/TraversalType2.cpp',
    'AppImage.cpp',
    'PayloadIterator.cpp',
    'Traversal.cpp',
)

core = declare_dependency(
    sources: core_files,
    dependencies: [
        libappimage_module_definitions,
        libappimage_hashlib,
        boost,
        xdg_utils_desktop_entry,
        libarchive,
        libsquashfuse,
    ],
)
