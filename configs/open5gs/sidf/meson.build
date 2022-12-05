# Copyright (C) 2022 by Sukchan Lee <acetcom@gmail.com>

# This file is part of Open5GS.

# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.

sidf_sysconfdir = join_paths(open5gs_sysconfdir, 'sidf')
meson.add_install_script(python3_exe, '-c',
        mkdir_p.format(sidf_sysconfdir))

sidf_security = '''
    private-key-1.pem
    public-key-1.pem
    private-key-2.pem
    public-key-2.pem
'''.split()

foreach file : sidf_security
    gen = configure_file(
            input : file,
            output : file,
            configuration : conf_data)
    meson.add_install_script(python3_exe, '-c',
            install_conf.format(gen, sidf_sysconfdir))
endforeach
