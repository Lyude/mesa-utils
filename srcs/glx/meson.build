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

deps = [
    common_dep,
    x11_dep,
    gl_dep,
    m_dep,
]

libpbutil = static_library('pbutil', 'pbutil.c', include_directories : inc_dir)

executables = [
    'glxinfo',
    'glxgears',
    'glxgears_pixmap',
]
foreach e : executables
    executable(e, [e + '.c', '../glinfo_common.c'],
               dependencies : deps, include_directories : inc_dir,
               install : true)
endforeach

executables = [
    'glxgears_fbconfig'
]
foreach e : executables
    executable(e, [e + '.c', '../glinfo_common.c'],
               dependencies: deps, include_directories : inc_dir,
               link_with : libpbutil,
               install : true)
endforeach
