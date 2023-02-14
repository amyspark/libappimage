core_files = files(
    'AppImage.cpp',
    'Traversal.cpp',
    'PayloadIterator.cpp',
    'impl/TraversalType1.cpp',
    'impl/TraversalType2.cpp',
    'impl/StreambufType1.cpp',
    'impl/StreambufType2.cpp',
)

core = declare_dependency(
    sources: core_files,
    dependencies: [boost, xdg_utils_desktop_entry, libarchive, libsquashfuse],
    link_with: [libappimage_hashlib],
    compile_args: libappimage_module_flags,
    include_directories: libappimage_include_directories,
)
