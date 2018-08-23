#project name and prog lang
project('com.github.ondb.hello-again', 'vala', 'c')

#include translation module
i18n = import('i18n')

#set translation domain
add_global_arguments('-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name()), language: 'c')

#create new exec, list files to compile, dependencies
executable(
  meson.project_name(),
  'src/Application.vala',
  dependencies: [
    dependency('gtk+-3.0')
  ],
  install: true
)

#translate and install .desktop file
i18n.merge_file(
  input      : join_paths('data', meson.project_name() + '.desktop.in'),
  output     : meson.project_name() + '.desktop',
  po_dir     : join_paths(meson.source_root(), 'po'),
  type       : 'desktop',
  install    : true,
  install_dir: join_paths(get_option('datadir'), 'applications')
)

#translate and install .appdata.xml file
i18n.merge_file(
  input      : join_paths('data', meson.project_name() + '.appdata.xml.in'),
  output     : meson.project_name() + 'appdata.xml',
  po_dir     : join_paths(meson.source_root(), 'po'),
  install    : true,
  install_dir: join_paths(get_option('datadir'), 'metainfo')
)
subdir('po')