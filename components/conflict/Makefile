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

#
# Copyright (c) 2011, Oracle and/or its affiliates. All rights reserved.
#

include ../../make-rules/shared-macros.mk

COMPONENT_NAME=		conflict
COMPONENT_VERSION=	20040901
IPS_COMPONENT_VERSION=	0.2004.9.1
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tgz
COMPONENT_PROJECT_URL=	http://invisible-island.net/conflict/conflict.html
COMPONENT_ARCHIVE_HASH=	sha1:fbf712f55c71c1c7c298609284fae00bdcbcc9c6
COMPONENT_ARCHIVE_URL=	ftp://invisible-island.net/$(COMPONENT_NAME)/$(COMPONENT_ARCHIVE)

include ../../make-rules/prep.mk
include ../../make-rules/configure.mk
include ../../make-rules/ips.mk

# Required to configure correctly.
COMPONENT_PRE_CONFIGURE_ACTION = \
	($(CLONEY) $(SOURCE_DIR) $(@D))

CONFIGURE_ENV += "CC=$(CC)"

# If the configure options are not explicitly set, then configure fails with:
# configure: warning: CC=/ws/onnv-tools/SUNWspro/sunstudio12.1/bin/cc: invalid host type
# configure: warning: CXX=/ws/onnv-tools/SUNWspro/sunstudio12.1/bin/CC: invalid host type
# configure: error: can only configure for one host and one target at a time
CONFIGURE_OPTIONS = --prefix=$(CONFIGURE_PREFIX)
CONFIGURE_OPTIONS += --mandir=$(CONFIGURE_MANDIR)

# common targets
build:		$(BUILD_32)

install:	$(INSTALL_32)

test:		build
	@cd $(BUILD_DIR_32); ./run_test.sh

BUILD_PKG_DEPENDENCIES =	$(BUILD_TOOLS)

include ../../make-rules/depend.mk
