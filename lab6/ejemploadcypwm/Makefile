#******************************************************************************
#
# Makefile - Rules for building the adcypwm example.
#
# Copyright (c) 2013-2020 Texas Instruments Incorporated.  All rights reserved.
# Software License Agreement
# 
# Texas Instruments (TI) is supplying this software for use solely and
# exclusively on TI's microcontroller products. The software is owned by
# TI and/or its suppliers, and is protected under applicable copyright
# laws. You may not combine this software with "viral" open-source
# software in order to form a larger program.
# 
# THIS SOFTWARE IS PROVIDED "AS IS" AND WITH ALL FAULTS.
# NO WARRANTIES, WHETHER EXPRESS, IMPLIED OR STATUTORY, INCLUDING, BUT
# NOT LIMITED TO, IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE APPLY TO THIS SOFTWARE. TI SHALL NOT, UNDER ANY
# CIRCUMSTANCES, BE LIABLE FOR SPECIAL, INCIDENTAL, OR CONSEQUENTIAL
# DAMAGES, FOR ANY REASON WHATSOEVER.
# 
# This is part of revision 2.2.0.295 of the EK-TM4C1294XL Firmware Package.
#
#******************************************************************************

#
# Defines the part type that this project uses.
#
PART=TM4C1294NCPDT

#
# The base directory for TivaWare.
#
ROOT=../../../..

#
# Include the common make definitions.
#
include ${ROOT}/makedefs

#
# Where to find header files that do not live in the source directory.
#
IPATH=../../../..

#
# The default rule, which causes the adcypwm example to be built.
#
all: ${COMPILER}
all: ${COMPILER}/adcypwm.axf

#
# The rule to clean out all the build products.
#
clean:
	@rm -rf ${COMPILER} ${wildcard *~}

#
# The rule to create the target directory.
#
${COMPILER}:
	@mkdir -p ${COMPILER}

#
# Rules for building the adcypwm example.
#
${COMPILER}/adcypwm.axf: ${COMPILER}/adcypwm.o
${COMPILER}/adcypwm.axf: ${COMPILER}/startup_${COMPILER}.o
${COMPILER}/adcypwm.axf: ${ROOT}/driverlib/${COMPILER}/libdriver.a
{COMPILER}/adcypwm.axf: ${ROOT}/utils/uartstdio.c  # Añadir uartstdio.c
${COMPILER}/adcypwm.axf: adcypwm.ld
SCATTERgcc_adcypwm=adcypwm.ld
ENTRY_adcypwm=ResetISR
CFLAGSgcc=-DTARGET_IS_TM4C129_RA1

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
