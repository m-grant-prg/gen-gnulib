#! /usr/bin/env bash
#########################################################################
#									#
# Script ID: src/man/1/Makefile.am					#
# Author: Copyright (C) 2018  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# Automake script file to generate gen-gnulib manual pages from source.	#
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


gen-gnulib.sh.1: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	$(edit) $(srcdir)/$(@F).man.in > $@.tmp
	targfile=$(@F);	\
	if [[ $$targfile == *"."* ]]; then \
		if [[ $${targfile##*.} == "" ]]; then \
			echo "Source file suffix used as section but empty."; \
			exit 1; \
		else \
			section=$${targfile##*.}; \
		fi; \
	else \
		echo "Source file suffix used as section but no dot & empty."; \
		exit 1; \
	fi; \
	txt2manwrap $(@F) $$section "gen-gnulib Manual" $@.tmp $@
	rm -f $@.tmp

gen-gnulib.sh.1: $(srcdir)/gen-gnulib.sh.1.man.in

man_MANS = gen-gnulib.sh.1

EXTRA_DIST = $(srcdir)/gen-gnulib.sh.1.man.in

CLEANFILES = *.tmp gen-gnulib.sh.1
