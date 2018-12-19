cloudproviders_plugin_dir = join_paths(plugin_dir, 'core')

cloudproviders_lib = meson.get_compiler('c').find_library('cloudproviders')
cloudproviders_vapi = meson.get_compiler('vala').find_library('cloudproviders', dirs: join_paths(meson.current_source_dir(), 'vapi'))
cloudproviders_dep = declare_dependency(dependencies: [cloudproviders_lib, cloudproviders_vapi])

shared_module(
    'pantheon-files-cloudproviders',
    'src/plugin.vala',
    'src/CloudManager.vala',
    dependencies: [ pantheon_files_core_dep, cloudproviders_dep],
    install: true,
    install_dir: cloudproviders_plugin_dir
)

install_data(
    'pantheon-files-cloudproviders.plug',
    install_dir: cloudproviders_plugin_dir
)
