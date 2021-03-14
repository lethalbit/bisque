subdir('include')

libbisque_deps = []

libbisque_srcs = files([

])

libbisque = library(
	'libbisque',
	libbisque_srcs,
	link_with: [ bisque_core ],
	gnu_symbol_visibility: 'inlineshidden',
	include_directories: [ libbisque_inc, bisque_core_inc ],
	dependencies: [ libbisque_deps ],
	install: true,
)
