subdir('include')

bisque_core_deps = []

bisque_core_srcs = files([

])

bisque_core = library(
	'bisque_core',
	bisque_core_srcs,
	gnu_symbol_visibility: 'inlineshidden',
	include_directories: [ bisque_core_inc ],
	dependencies: [ bisque_core_deps ],
	install: true,
)
