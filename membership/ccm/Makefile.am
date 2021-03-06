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
			-I$(top_builddir)/libltdl -I$(top_srcdir)/libltdl \
                        -I$(includedir)/clplumbing

halibexecdir		= $(libexecdir)/@HB_PKG@
ccmlibdir		= $(halibexecdir)

ccmdir			= $(HA_VARRUNDIR)/$(HB_PKG)/ccm
apigid			= @HA_APIGID@
ccmuid			= @HA_CCMUID@
gliblib			= @GLIBLIB@


AM_CFLAGS			= @CFLAGS@

noinst_HEADERS		= ccm.h ccmlib.h

## libraries

lib_LTLIBRARIES		= libccmclient.la libclm.la


## binary progs
ccmlib_PROGRAMS	= ccm ccm_testclient

## SOURCES
ccm_SOURCES	= ccm.c \
		  ccmmisc.c \
		  ccmgraph.c \
		  ccmversion.c \
		  ccmupdate.c \
		  ccmllm.c \
		  ccmbitmap.c \
		  ccm.h \
		  ccmmain.c \
		  ccmclient.c \
		  ccmmsg.h   \
		  ccmmsg.c   \
		  ccm_statemachine.c \
		  ccmmisc.h 	\
		  ccmmem.c

ccm_LDADD	= -lplumb	\
		$(top_builddir)/lib/hbclient/libhbclient.la  	\
		$(gliblib) \
		  -lpils


ccm_LDFLAGS		= 

ccm_testclient_SOURCES	= ccm_testclient.c
ccm_testclient_LDADD	= libccmclient.la \
			  -lplumb \
			  $(gliblib) \
			  -lpils


libccmclient_la_SOURCES	= ccmlib_memapi.c ccmlib_eventapi.c ccmlib.h
libccmclient_la_LDFLAGS	= -version-info 1:0:0
libccmclient_la_LIBADD	= $(gliblib) \
			  -lplumb

## library libclm.la
libclmdir		= $(halibexecdir)

## binary program
libclm_PROGRAMS		= clmtest

libclm_la_SOURCES	= ccmlib_clm.c

## Add -DPOSIX_THREADS to CFLAGS to compile a thread-safe version library
libclm_la_CFLAGS	= -g #-DPOSIX_THREADS
libclm_la_LDFLAGS	= -version-info 1:0:0
libclm_la_LIBADD        = libccmclient.la \
			  $(gliblib) \
			  -lplumb

clmtest_SOURCES		= clmtest.c
clmtest_LDADD		= libclm.la libccmclient.la \
			  -lplumb \
			  $(gliblib)\
			  -lpils


## additional Makefile targets
# additional installations not covered normally
install-exec-local:
	$(mkinstalldirs) $(DESTDIR)$(ccmdir)
	-chgrp $(apigid) $(DESTDIR)/$(ccmdir)
	-chown $(ccmuid) $(DESTDIR)/$(ccmdir)
	chmod 750 $(DESTDIR)/$(ccmdir)


uninstall-local:
	rm -fr $(DESTDIR)$(ccmdir)
