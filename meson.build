#project name and prog lang
project('com.github.ondb.hello-again', 'vala', 'c')

#create new exec, list files to compile, dependencies
executable(
  meson.project_name(),
  'src/Application.vala',
  dependencies: [
    dependency('gtk+-3.0')
  ],
  install: true
)

#install .desktop file
install_data(
  join_paths('data', meson.project_name() + '.desktop'),
  install_dir: join_paths(get_option('datadir'), 'applications')
)

#install .appdata.xml
install_data(
  join_paths('data', meson.project_name() + '.appdata.xml'),
  install_dir: join_paths(get_option('datadir'), 'metainfo')
)