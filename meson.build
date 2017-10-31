# Copyright © 2017 Red Hat

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

project('mesa-utils', 'c', license : 'MIT')

host_system = host_machine.system()
cc = meson.get_compiler('c')

with_egl = get_option('egl')

epoxy_dep = dependency('epoxy', required: true)

common_dep = [
    epoxy_dep,
]

if cc.get_id() == 'msvc' # TODO
    error('MSVC support TODO, sorry')
else
    default_c_flags = [
        '-Wall',
        '-Wpointer-arith',
        '-Wstrict-prototypes',
        '-Wmissing-prototypes',
        '-Wmissing-declarations',
        '-Wnested-externs',
        '-Wno-strict-aliasing',
        '-Wbad-function-cast',
        '-Wold-style-definition',
        '-Wdeclaration-after-statement',
    ]
endif

foreach f : default_c_flags
    if cc.has_argument(f)
        add_project_arguments(f, language : 'c')
    endif
endforeach

subdir('srcs')
