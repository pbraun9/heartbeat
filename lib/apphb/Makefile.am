#
# apphb: OCF application heartbeat library
#
# Copyright (C) 2002 Alan Robertson, International Business Machines
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
			-I$(top_builddir)/linux-ha -I$(top_srcdir)/linux-ha  \
			-I$(top_builddir)/libltdl -I$(top_srcdir)/libltdl


AM_CFLAGS		= @CFLAGS@

gliblib			= @GLIBLIB@

## libraries

lib_LTLIBRARIES		= libapphb.la

libapphb_la_SOURCES	= apphb.c	

if ENABLE_THREAD_SAFE
libapphb_la_CFLAGS	= -DTHREAD_SAFE -D_REENTRANT
else
libapphb_la_CFLAGS	= -lpthread
endif

libapphb_la_LDFLAGS	= -version-info 2:0:0 
libapphb_la_LIBADD	= $(gliblib) \
			  -lplumb
