project(
	'bisque',
	'cpp',
	default_options: [
		'cpp_std=gnu++17',
		'warning_level=3',
		'buildtype=debugoptimized',
		'b_ndebug=if-release',
		'b_lto=true'
	],
	version: '0.1',
	license: [
		'GPL-3.0-only',
		'LGPL-3.0-or-later'
	],
	meson_version: '>=0.57.0',
	subproject_dir: 'deps'
)

cxx = meson.get_compiler('cpp', native: true)

extended_warnings = [
	'-Wdouble-promotion',
	'-Wformat=2',
	'-Wformat-overflow=2',
	'-Wformat-signedness',
	'-Wformat-truncation',
	'-Wnull-dereference',
	'-Wmissing-attributes',
	'-Wmissing-braces',
	'-Wsequence-point',
	'-Wreturn-type',
	'-Wunused',
	'-Wunused-local-typedefs',
	'-Wunused-const-variable=2',
	'-Wmaybe-uninitialized',
	'-Wunknown-pragmas',
	'-Wstrict-aliasing',
	'-Wstrict-overflow=3',
	'-Wstring-compare',
	'-Wstringop-overflow',
	'-Warith-conversion',
	'-Wvla-parameter',
	'-Wduplicated-branches',
	'-Wshadow=local',
	'-Wunsafe-loop-optimizations',
	'-Wbad-function-cast',
	'-Wcast-qual',
	'-Wcast-align=strict',
	'-Wcast-function-type',
	'-Wconversion',
	'-Wdangling-else',
	'-Wsign-conversion',
	'-Wfloat-conversion',
	'-Wpacked',
	'-Wpadded',
	'-Wredundant-decls',
	'-Winline',
	'-Wvla',
	'-Wstack-protector',
	'-Wunsuffixed-float-constant',
	'-Wimplicit-fallthrough',
]

add_project_arguments(
	cxx.get_supported_arguments(extended_warnings),
	language: 'cpp'
)

subdir('bisque-core')
subdir('libbisque')


if not meson.is_subproject()
	pkgconfig = import('pkgconfig')

	pkgconfig.generate(
		subdirs: '.',
		name: 'bisque-core',
		filebase: 'bisque-core',
		libraries: [ bisque_core ],
		version: meson.project_version(),
		description: 'A collection of headers containing useful tools and gadgets for building C++ programs'
	)

	pkgconfig.generate(
		subdirs: '.',
		name: 'libbisque',
		filebase: 'libbisque',
		libraries: [ libbisque, bisque_core ],
		version: meson.project_version(),
		description: 'A collection of headers containing useful tools and gadgets for building C++ programs'
	)
endif

bisque_core_dep = declare_dependency(
	dependencies: [ bisque_core_deps],
	include_directories: [ bisque_core_inc ],
	link_with: [ bisque_core ],
	version: meson.project_version()
)

libbisque_dep = declare_dependency(
	dependencies: [ libbisque_deps ],
	include_directories: [ libbisque_inc ],
	link_with: [ libbisque ],
	version: meson.project_version()
)
