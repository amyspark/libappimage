temporarydirectory_files = files(
    'TemporaryDirectory.cpp'
)

temporarydirectory_lib = library(
    'temporarydirectory',
    temporarydirectory_files,
)

temporarydirectory = declare_dependency(
    link_with: temporarydirectory_lib,
    include_directories: include_directories('.')
)
