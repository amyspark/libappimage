fixtures = declare_dependency(
    include_directories: include_directories('.'),
    dependencies: [test_dep, gtest, xdg_basedir],
)

test_libappimage_files = files(
    'test_libappimage.cpp',
)

test_libappimage = executable(
    'test_libappimage',
    test_libappimage_files,
    dependencies: [fixtures, libappimage, libsquashfuse, libglib, libgobject],
)

test_xdg_basedir_files = files(
    'test-xdg-basedir.cpp',
)

test_xdg_basedir = executable(
    'test-xdg-basedir',
    test_xdg_basedir_files,
    dependencies: fixtures,
)

test('test_libappimage', test_libappimage)
test('test-xdg-basedir', test_xdg_basedir)

test_shared_files = files(
    'test_shared.cpp',
)

test_shared = executable(
    'test_shared',
    test_shared_files,
    dependencies: [fixtures, libappimage_shared],
    # needed for some const->non-const conversions
    cpp_args: cxx.get_supported_arguments('-fpermissive')
)

test('test_shared', test_shared)
