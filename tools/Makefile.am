#
# heartbeat: Linux-HA heartbeat code
#
# Copyright (C) 2001 Michael Moerz
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

EXTRA_DIST		= 

apigid			= @HA_APIGID@
habindir		= @bindir@
halibdir		= $(libdir)/@HB_PKG@
hanoarchdir		= @HA_NOARCHDATAHBDIR@
gliblib			= @GLIBLIB@

habin_PROGRAMS		= cl_status cl_respawn

cl_status_SOURCES	= cl_status.c
cl_status_LDADD		= $(top_builddir)/lib/hbclient/libhbclient.la	\
			  $(top_builddir)/membership/ccm/libclm.la	\
			  $(top_builddir)/membership/ccm/libccmclient.la \
			  -lplumb	\
			  $(gliblib)					\
			  $(top_builddir)/replace/libreplace.la

cl_respawn_SOURCES	= cl_respawn.c
cl_respawn_LDADD	= -lplumb	\
			  $(top_builddir)/lib/apphb/libapphb.la 	\
			  $(gliblib)					\
			  $(top_builddir)/replace/libreplace.la

install-data-hook:    # install-exec-hook doesn't work (!)
	-chgrp $(apigid) $(DESTDIR)/$(habindir)/cl_status
	-chmod g+s,a-w $(DESTDIR)/$(habindir)/cl_status

.PHONY: install-exec-hook
