libudt_dep = dependency('udt')
threads_dep = dependency('threads')
m_dep = cxx.find_library('m')

app_args = [
    '-D@0@'.format(get_option('os')),
    '-finline-functions',
]

app_deps = [
    libudt_dep,
    threads_dep,
    m_dep,
]

if get_option('os') == 'UNIX'
    app_deps += cxx.find_library('socket')
endif

if get_option('os') == 'SUNOS'
    app_deps += cxx.find_library('rt')
    app_deps += cxx.find_library('socket')
endif

executable('appserver', 'appserver.cpp', cpp_args: app_args, dependencies: app_deps)

executable('appclient', 'appclient.cpp', cpp_args: app_args, dependencies: app_deps)

executable('recvfile', 'recvfile.cpp', cpp_args: app_args, dependencies: app_deps)

executable('sendfile', 'sendfile.cpp', cpp_args: app_args, dependencies: app_deps)

executable('testapp', 'test.cpp', cpp_args: app_args, dependencies: app_deps)
