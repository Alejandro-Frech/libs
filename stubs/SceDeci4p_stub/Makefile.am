# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceDeci4p-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x28578fe8 0x3bc66bd8 0x5a4cdf97 0x63b0c50f 	\
	0x73371f35 0x971e1c66 0xc4e1d86d 0xcda3aaac

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceDeci4p_stub.a
libSceDeci4p_stub_a_SOURCES = SceDeci4pUserp_stub.S
am_libSceDeci4p_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceDeci4p_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceDeci4p_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceDeci4p_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
