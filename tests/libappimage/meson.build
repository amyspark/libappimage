subdir('legacy')
subdir('temporarydirectory')

if desktop_integration.enabled()
    subdir('desktop_integration')
endif

test_libappimagepp_files = files(
    'TestLibappimage++.cpp',

    'core/impl/TestTraversalType1.cpp',
    'core/impl/TestTraversalType2.cpp',

    'utils/TestMagicBytesChecker.cpp',
    'utils/TestUtilsElf.cpp',
    'utils/TestIconHandle.cpp',
    'utils/TestLogger.cpp',
    'utils/TestPayloadEntriesCache.cpp',
    'utils/TestResourcesExtractor.cpp',
    'utils/StringSanitizerTest.cpp',
)

test_libappimagepp = executable(
    'test_libappimage++',
    test_libappimagepp_files,
    dependencies: [test_definitions, temporarydirectory, libappimage, libarchive, libsquashfuse, xdg_utils_desktop_entry, xdg_utils_base_dir, gtest],
)

test('test_libappimage++', test_libappimagepp)
