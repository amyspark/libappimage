temporarydirectory_files = files(
    'TemporaryDirectory.cpp'
)

temporarydirectory = library(
    'temporarydirectory',
    temporarydirectory_files,
)

temporarydirectory_dep = declare_dependency(
    link_with: temporarydirectory,
    include_directories: include_directories('.')
)
