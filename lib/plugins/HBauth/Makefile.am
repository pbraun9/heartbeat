#
# InterfaceMgr: Interface manager plugins for Linux-HA
#
# Copyright (C) 2001 Alan Robertson
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
			-I$(top_builddir)/libltdl -I$(top_srcdir)/libltdl  \
			-I$(top_builddir)/lib/upmls -I$(top_srcdir)/lib/upmls

AM_CFLAGS			= @CFLAGS@

## libraries

halibdir		= $(libdir)/@HB_PKG@
plugindir		= $(halibdir)/plugins/HBauth
plugin_LTLIBRARIES	= md5.la crc.la sha1.la

md5_la_SOURCES	= md5.c
md5_la_LDFLAGS	= -export-dynamic -module -avoid-version
md5_la_LIBADD	= -lplumb

crc_la_SOURCES	= crc.c
crc_la_LDFLAGS	= -export-dynamic -module -avoid-version

sha1_la_SOURCES	= sha1.c
sha1_la_LDFLAGS	= -export-dynamic -module -avoid-version


