libudt_dep = dependency('udt')
threads_dep = dependency('threads')
threads_dep = dependency('threads')

app_args = []
if host_system != 'windows'
    app_args += [
        '-finline-functions',
    ]
endif

app_deps = [
    libudt_dep,
    threads_dep,
]
if host_system == 'windows'
    app_deps += cxx.find_library('ws2_32', required: true)
endif

if host_system == 'linux'
    app_deps += cxx.find_library('m')
    app_deps += cxx.find_library('socket')
endif

if host_system == 'sunos'
    app_deps += cxx.find_library('rt')
    app_deps += cxx.find_library('socket')
endif

executable('appserver', 'appserver.cpp', cpp_args: app_args, dependencies: app_deps)

executable('appclient', 'appclient.cpp', cpp_args: app_args, dependencies: app_deps)

executable('recvfile', 'recvfile.cpp', cpp_args: app_args, dependencies: app_deps)

executable('sendfile', 'sendfile.cpp', cpp_args: app_args, dependencies: app_deps)

executable('testapp', 'test.cpp', cpp_args: app_args, dependencies: app_deps)
