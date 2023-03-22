pkgdatadir = join_paths(get_option('prefix'), get_option('datadir'), meson.project_name())
moduledir = join_paths(pkgdatadir, 'appd')

python = import('python')

conf = configuration_data()
conf.set('PYTHON', python.find_installation('python3').full_path())
conf.set('pkgdatadir', pkgdatadir)
configure_file(
            input: 'appd.in',
           output: 'appd',
    configuration: conf,
          install: true,
      install_dir: get_option('bindir'),
     install_mode: 'r-xr--r--'
)

appd_sources = [
    '__init__.py',
    'main.py'
]

install_data(appd_sources, install_dir: moduledir)
