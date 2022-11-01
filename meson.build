project('udt', ['cpp'],
        version: '4.11',
        license: 'NCSA',
        default_options: [
            'default_library=static',
            'warning_level=1',
            'optimization=3'
        ])

host_system = host_machine.system()
cxx = meson.get_compiler('cpp')

if get_option('arch') == 'IA32'
    add_project_arguments('-DIA32', language: ['cpp'])
elif get_option('arch') == 'powerpc'
    add_project_arguments('-mcpu=powerpc', language: ['cpp'])
elif get_option('arch') == 'SPARC'
    add_project_arguments('-DSPARC', language: ['cpp'])
elif get_option('arch') == 'IA64'
    add_project_arguments('-DIA64', language: ['cpp'])
elif get_option('arch') == 'AMD64'
    add_project_arguments('-DAMD64', language: ['cpp'])
endif

subdir('src')
subdir('app')
