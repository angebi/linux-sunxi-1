#------------------------------------------------------------------------------
# <copyright file="makefile" company="Atheros">
#    Copyright (c) 2005-2007 Atheros Corporation.  All rights reserved.
# 
#
# Permission to use, copy, modify, and/or distribute this software for any
# purpose with or without fee is hereby granted, provided that the above
# copyright notice and this permission notice appear in all copies.
#
# THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
# WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
# MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
# ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
# WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
# ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
# OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
#
#
#------------------------------------------------------------------------------
#==============================================================================
# Author(s): ="Atheros"
#==============================================================================
CC := $(ATH_CROSS_COMPILE_TYPE)gcc
AR := $(ATH_CROSS_COMPILE_TYPE)ar
RM := $(ATH_CROSS_COMPILE_TYPE)rm

KERNEL_SRC :=$(ATH_LINUXPATH)
PAL_SRC=pal_api.c pal_intf.c pal_util.c
PAL_OBJ=pal_api.o pal_intf.o pal_util.o
PAL_INTF_LIB=libpal_intf.a
PAL_APP=pal_app

all:
	$(CC) -Wall -c -I./ -I$(KERNEL_SRC)/include -I../../include -I../../../include -I../../wlan/include -I../../os/linux/include  $(PAL_SRC)
	$(AR) -crs $(PAL_INTF_LIB) $(PAL_OBJ)
	$(CC) -Wall -I./ -I$(KERNEL_SRC)/include -I../../include -I../../../include -I../../wlan/include -I../../os/linux/include bt_inp.c $(PAL_INTF_LIB) -o $(PAL_APP) -lpthread

clean:
	$(RM) $(PAL_OBJ) $(PAL_INTF_LIB) $(PAL_APP)
