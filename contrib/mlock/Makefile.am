#
# heartbeat: multi clients lock test code
#
# Copyright (C) 2004 Guochun Shi(gshi@ncsa.uiuc.edu)
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, see <http://www.gnu.org/licenses/>.
#
MAINTAINERCLEANFILES    = Makefile.in

AM_CPPFLAGS		= -I$(top_builddir)/include -I$(top_srcdir)/include \
                        -I$(top_builddir)/linux-ha -I$(top_srcdir)/linux-ha \
                        -I$(top_builddir)/libltdl -I$(top_srcdir)/libltdl

halibexecdir		= $(libexecdir)/@HB_PKG@

havarlibdir             = $(localstatedir)/lib/@HB_PKG@


halibexec_PROGRAMS      = mlock

## SOURCES
mlock_SOURCES          = mlock.c
mlock_LDADD            =$(GLIBLIB) $(top_builddir)/replace/libreplace.la


## additional Makefile targets
# additional installations not covered normally
install-exec-local:

uninstall-local:

