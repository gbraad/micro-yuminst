# Copyright (C) 2011,2013 Colin Walters <walters@verbum.org>
#
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2 of the License, or (at your option) any later version.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this library; if not, write to the
# Free Software Foundation, Inc., 59 Temple Place - Suite 330,
# Boston, MA 02111-1307, USA.

include Makefile-decls.am

SUBDIRS += .

ACLOCAL_AMFLAGS += -I m4 ${ACLOCAL_FLAGS}
AM_CPPFLAGS += -DDATADIR='"$(datadir)"' \
	-DLIBEXECDIR='"$(libexecdir)"' \
	-DLOCALEDIR=\"$(datadir)/locale\" \
	-DGLIB_VERSION_MIN_REQUIRED=GLIB_VERSION_2_44 -DGLIB_VERSION_MAX_ALLOWED=GLIB_VERSION_2_44
AM_CFLAGS += -std=gnu99 $(WARN_CFLAGS)

EXTRA_DIST += autogen.sh COPYING

GITIGNOREFILES += build-aux/ gtk-doc.make config.h.in aclocal.m4

SED_SUBST = sed \
        -e 's,[@]libexecdir[@],$(libexecdir),g' \
        $(NULL)

include Makefile-microyuminst.am
include Makefile-hif.am

-include $(top_srcdir)/git.mk
