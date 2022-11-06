project('udt', ['cpp'],
        version: '4.11',
        license: 'NCSA',
        default_options: [
            'default_library=static',
            'warning_level=1',
            'optimization=3'
        ])

host_system = host_machine.system()
host_cpu_family = host_machine.cpu_family()

cxx = meson.get_compiler('cpp')

if host_system == 'windows'
    add_project_arguments('-DWIN32', language: ['cpp'])
    add_project_arguments('-DUDT_EXPORTS', language: ['cpp'])
else
    if host_system == 'linux'
        add_project_arguments('-DLINUX', language: ['cpp'])
    elif host_system == 'darwin'
        add_project_arguments('-DOSX', language: ['cpp'])
    endif

    if host_cpu_family == 'x86'
        add_project_arguments('-DIA32', language: ['cpp'])
    elif host_cpu_family == 'ppc'
        add_project_arguments('-mcpu=powerpc', language: ['cpp'])
    elif host_cpu_family == 'sparc'
        add_project_arguments('-DSPARC', language: ['cpp'])
    elif host_cpu_family == 'ia64'
        add_project_arguments('-DIA64', language: ['cpp'])
    elif host_cpu_family == 'x86_64'
        add_project_arguments('-DAMD64', language: ['cpp'])
    endif
endif

subdir('src')
subdir('app')
