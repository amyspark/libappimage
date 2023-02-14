test_definitions = [
    '-DTEST_DATA_DIR="@0@"'.format(meson.current_source_dir() / 'data' / ''),
    '-DGIT_COMMIT="AppImageKit unit tests"'
]

test_dep = declare_dependency(
    compile_args: test_definitions,
)

subdir('libappimage')
