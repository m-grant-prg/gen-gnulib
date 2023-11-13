#########################################################################
#									#
# Author: Copyright (C) 2018, 2021, 2023  Mark Grant			#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
# Automake script file to generate gen-gnulib scripts from source.	#
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
