subdir('legacy')
subdir('temporarydirectory')

if desktop_integration.enabled()
    subdir('desktop_integration')
endif

test_libappimagepp_files = files(
    'core/impl/TestTraversalType1.cpp',
    'core/impl/TestTraversalType2.cpp',
    'utils/StringSanitizerTest.cpp',
    'utils/TestIconHandle.cpp',
    'utils/TestLogger.cpp',
    'utils/TestMagicBytesChecker.cpp',
    'utils/TestPayloadEntriesCache.cpp',
    'utils/TestResourcesExtractor.cpp',
    'utils/TestUtilsElf.cpp',
    'TestLibappimage++.cpp',
)

test_libappimagepp = executable(
    'test_libappimage++',
    test_libappimagepp_files,
    dependencies: [
        test_definitions,
        temporarydirectory,
        libappimage,
        libarchive,
        libsquashfuse,
        xdg_utils_desktop_entry,
        xdg_utils_base_dir,
        gtest,
    ],
)

test('test_libappimage++', test_libappimagepp)
