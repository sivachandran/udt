libudt_sources = [
    'api.cpp',
    'buffer.cpp',
    'cache.cpp',
    'ccc.cpp',
    'channel.cpp',
    'common.cpp',
    'core.cpp',
    'epoll.cpp',
    'list.cpp',
    'md5.cpp',
    'packet.cpp',
    'queue.cpp',
    'window.cpp',
    'udtc.cpp',
]

libudt_args = [
    '-D@0@'.format(get_option('os')),
    '-finline-functions',
    '-fno-strict-aliasing',
    '-fvisibility=hidden',
]

libudt_lib = library('udt', libudt_sources, cpp_args: libudt_args, pic: true)


libudt_dep = declare_dependency(
    include_directories: include_directories('.'),
    link_with: libudt_lib,
)

meson.override_dependency('udt', libudt_dep)
