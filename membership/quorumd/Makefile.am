#
#  Author: Huang Zhen <zhenhltc@cn.ibm.com>
#  Copyright (c) 2006 International Business Machines
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
MAINTAINERCLEANFILES = Makefile.in

AM_CPPFLAGS	= -I$(top_builddir)/include  -I$(top_srcdir)/include     \
                  -I$(top_builddir)/libltdl  -I$(top_srcdir)/libltdl     \
		  -I$(top_builddir)/linux-ha -I$(top_srcdir)/linux-ha    \
		  -I$(top_builddir)          -I$(top_srcdir)


COMMONLIBS	=  -lplumb   \
		   $(GLIBLIB)

halibexecdir	=  $(libexecdir)/@HB_PKG@

halibexec_PROGRAMS 	=  quorumd quorumdtest
quorumd_SOURCES =  quorumd.c
quorumd_LDADD 	=  $(COMMONLIBS)
quorumd_LDFLAGS = $(GNUTLSLIBS)
quorumd_CFLAGS = $(AM_CPPFLAGS) $(GNUTLSHEAD)

quorumdtest_SOURCES =  quorumdtest.c
quorumdtest_LDADD =  $(COMMONLIBS)
quorumdtest_LDFLAGS = $(GNUTLSLIBS)
quorumdtest_CFLAGS = $(AM_CPPFLAGS) $(GNUTLSHEAD)
