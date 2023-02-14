test_definitions = declare_dependency(
    compile_args: [
        '-DTEST_DATA_DIR="@0@"'.format(meson.current_source_dir() / 'data' / ''),
        '-DGIT_COMMIT="AppImageKit unit tests"',
    ],
)

subdir('libappimage')
