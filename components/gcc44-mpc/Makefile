#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright (c) 2011, OpenIndiana project. All rights reserved.
#
include ../../make-rules/shared-macros.mk

COMPONENT_NAME=		mpc
COMPONENT_VERSION=	0.8.1
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	sha1:5ef03ca7aee134fe7dfecb6c9d048799f0810278
COMPONENT_ARCHIVE_URL=	http://www.multiprecision.org/mpc/download/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL=  http://www.multiprecision.org/mpc/

include ../../make-rules/prep.mk
include ../../make-rules/configure.mk
include ../../make-rules/ips.mk

GCC_ROOT=/usr/gcc/4.4
COMPILER=gcc

CPPFLAGS+= -fexceptions

CONFIGURE_PREFIX    =           /usr/gcc/4.4
CONFIGURE_OPTIONS  +=           CPPFLAGS="$(CPPFLAGS)"
CONFIGURE_OPTIONS  +=           -with-gmp=$(CONFIGURE_PREFIX)
CONFIGURE_OPTIONS  +=           -with-mpfr=$(CONFIGURE_PREFIX)
CONFIGURE_OPTIONS  +=           --disable-static

include ../../make-rules/shared-targets.mk

build:		$(BUILD_32)

install:	$(INSTALL_32)

BUILD_PKG_DEPENDENCIES =	$(BUILD_TOOLS)

include ../../make-rules/depend.mk
