#! /usr/bin/env bash
#########################################################################
#									#
# Script ID: src/prg/bash/Makefile.am					#
# Author: Copyright (C) 2018  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# Automake script file to generate gen-gnulib scripts from source.	#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 07/02/2018	MG	1.0.1	Initial release.			#
# 09/02/2018	MG	1.0.2	Change file's header for new directory	#
#				names.					#
#									#
#########################################################################


gen-gnulib.sh: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).in > $@.tmp
	mv $@.tmp $@
	chmod a+x $@

gen-gnulib.sh: $(srcdir)/gen-gnulib.sh.in

bin_SCRIPTS = gen-gnulib.sh

EXTRA_DIST = $(srcdir)/gen-gnulib.sh.in

CLEANFILES = *.tmp gen-gnulib.sh
