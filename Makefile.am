#! /usr/bin/env bash
#########################################################################
#									#
# Script ID: ./Makefile.am						#
# Author: Copyright (C) 2018  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0					#
#									#
# Purpose:								#
# Automake script file to generate gen-gnulib project from source.	#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 07/02/2018	MG	1.0.1	Initial release.			#
# 09/02/2018	MG	1.0.2	Shorten directory names to reduce	#
#				overall path length.			#
# 27/04/2018	MG	1.0.3	Add srctarball target to build a source	#
#				tarball in the build directory. Uses	#
#				git archive to archive HEAD.		#
# 10/06/2018	MG	1.0.4	Add info messages to srctarball target.	#
# 31/10/2018	MG	1.0.5	Change srctarball target to build with	#
#				src between package name and version in	#
#				filename.				#
#									#
#########################################################################


ACLOCAL_AMFLAGS = -I m4


SUBDIRS = src/prg/bash src/man/1


srctarball:
	@cwd="$${PWD}" && \
	targ="$${cwd}/@PACKAGE_TARNAME@-src-@PACKAGE_VERSION@.tar.gz" && \
	cd @srcdir@ && \
	echo "making srctarball from @srcdir@" && \
	echo "GA	$${targ}" && \
	git archive --format=tar.gz \
		--prefix=@PACKAGE_TARNAME@-@PACKAGE_VERSION@/ \
		--output=$${targ} \
		HEAD && \
	cd -

