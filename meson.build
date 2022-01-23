project(
    'libgbinder', 'c',
    version : '1.1.9',
)

pc = import('pkgconfig')

glib = dependency('glib-2.0')
gobject = dependency('gobject-2.0')
libglibutil = dependency('libglibutil')
threads = dependency('threads')

headers = [
    'include/gbinder.h',
    'include/gbinder_bridge.h',
    'include/gbinder_buffer.h',
    'include/gbinder_client.h',
    'include/gbinder_eventloop.h',
    'include/gbinder_local_object.h',
    'include/gbinder_local_reply.h',
    'include/gbinder_local_request.h',
    'include/gbinder_reader.h',
    'include/gbinder_remote_object.h',
    'include/gbinder_remote_reply.h',
    'include/gbinder_remote_request.h',
    'include/gbinder_servicemanager.h',
    'include/gbinder_servicename.h',
    'include/gbinder_types.h',
    'include/gbinder_writer.h',
]

install_headers(headers, subdir : 'gbinder')

sources = [
    'src/gbinder_bridge.c',
    'src/gbinder_buffer.c',
    'src/gbinder_cleanup.c',
    'src/gbinder_client.c',
    'src/gbinder_config.c',
    'src/gbinder_driver.c',
    'src/gbinder_eventloop.c',
    'src/gbinder_io.c',
    'src/gbinder_io_32.c',
    'src/gbinder_io_64.c',
    'src/gbinder_ipc.c',
    'src/gbinder_local_object.c',
    'src/gbinder_local_reply.c',
    'src/gbinder_local_request.c',
    'src/gbinder_log.c',
    'src/gbinder_proxy_object.c',
    'src/gbinder_reader.c',
    'src/gbinder_remote_object.c',
    'src/gbinder_remote_reply.c',
    'src/gbinder_remote_request.c',
    'src/gbinder_rpc_protocol.c',
    'src/gbinder_servicemanager.c',
    'src/gbinder_servicemanager_aidl.c',
    'src/gbinder_servicemanager_aidl2.c',
    'src/gbinder_servicemanager_hidl.c',
    'src/gbinder_servicename.c',
    'src/gbinder_servicepoll.c',
    'src/gbinder_system.c',
    'src/gbinder_writer.c',
]

incdir = include_directories('include')

lib = library(
    'gbinder',
    sources : sources,
    dependencies : [glib, gobject, libglibutil, threads],
    include_directories : incdir,
    version : meson.project_version(),
    install : true,
)

pc.generate(
    lib,
    name : 'libgbinder',
    description : 'Binder client library',
    subdirs : 'gbinder',
    requires : [libglibutil],
)
