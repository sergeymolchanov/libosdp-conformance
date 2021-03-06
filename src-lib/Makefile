# Make file for libosdp

#  (C)Copyright 2017-2020 Smithee Solutions LLC
#  (C)Copyright 2015-2017 Smithee,Spelvin,Agnew & Plinge, Inc.

#  Support provided by the Security Industry Association
#  http://www.securityindustry.org

#  Licensed under the Apache License, Version 2.0 (the "License");
#  you may not use this file except in compliance with the License.
#  You may obtain a copy of the License at
 
#    http://www.apache.org/licenses/LICENSE-2.0
 
#  Unless required by applicable law or agreed to in writing, software
#  distributed under the License is distributed on an "AS IS" BASIS,
#  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#  See the License for the specific language governing permissions and
#  limitations under the License.


OUTLIB=libosdp.a

# built with gcc.  note it also builds with clang.
CC=gcc
#CC=clang

CFLAGS=-c -DOSDP_CONFORMANCE -g -I../include -I/opt/osdp-conformance/include \
  -Wall -Werror


all:	${OUTLIB}

build:	all
	mkdir -p ../opt/osdp-conformance/lib
	cp ${OUTLIB} ../opt/osdp-conformance/lib

clean:
	rm -f core *.o ${OUTLIB}

libosdp.a:	\
	oo-actions.o oo-api.o oo-bio.o \
	  oo-cmdbreech.o oo-initialize.o oo-process.o \
	  oo-util.o oo-util2.o oo-util3.o \
	  oo-logprims.o oo-printmsg.o oo-xpm-actions.o oo-xwrite.o \
	  oo-crc.o oo-conformance.o \
	  oo-files.o oo-logmsg.o oo-prims.o \
	  oo-secure.o oo-secure-actions.o oo-settings.o oo-ui.o
	ar r libosdp.a \
	  oo-actions.o oo-api.o oo-bio.o \
	  oo-cmdbreech.o oo-initialize.o oo-process.o oo-util.o oo-util2.o \
	  oo-util3.o oo-logprims.o oo-printmsg.o oo-xpm-actions.o oo-xwrite.o \
	  oo-conformance.o oo-crc.o oo-files.o \
	  oo-logmsg.o oo-prims.o oo-secure.o \
	  oo-secure-actions.o oo-settings.o oo-ui.o

oo-actions.o:	oo-actions.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-actions.c

oo-api.o:	oo-api.c ../include/osdp-tls.h ../include/open-osdp.h
	${CC} ${CFLAGS} oo-api.c

oo-bio.o:	oo-bio.c ../include/osdp-tls.h ../include/open-osdp.h
	${CC} ${CFLAGS} oo-bio.c

oo-cmdbreech.o:	oo-cmdbreech.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-cmdbreech.c

oo-initialize.o:	oo-initialize.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-initialize.c

oo-process.o:	oo-process.c
	${CC} ${CFLAGS} oo-process.c

oo-util.o:	oo-util.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-util.c

oo-util2.o:	oo-util2.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-util2.c

oo-util3.o:	oo-util3.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-util3.c

oo-logprims.o:	oo-logprims.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-logprims.c

oo-printmsg.o:	oo-printmsg.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-printmsg.c

oo-xpm-actions.o:	oo-xpm-actions.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-xpm-actions.c

oo-xwrite.o:	oo-xwrite.c ../include/open-osdp.h ../include/iec-xwrite.h
	${CC} ${CFLAGS} oo-xwrite.c

# different as it uses source here by inclusion
oo-conformance.o:	oo-conformance.c oo-SKIP.c
	${CC} ${CFLAGS} -I. oo-conformance.c

oo-crc.o:	oo-crc.c
	${CC} ${CFLAGS} oo-crc.c

oo-files.o:	oo-files.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-files.c

oo-logmsg.o:	oo-logmsg.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-logmsg.c

oo-prims.o:	oo-prims.c /opt/osdp-conformance/include/open-osdp.h
	${CC} ${CFLAGS} oo-prims.c

oo-secure.o:	oo-secure.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-secure.c

oo-settings.o:	oo-settings.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-settings.c

oo-secure-actions.o:	oo-secure-actions.c ../include/open-osdp.h
	${CC} ${CFLAGS} oo-secure-actions.c

oo-ui.o:	oo-ui.c ../include/open-osdp.h ../include/iec-xwrite.h
	${CC} ${CFLAGS} oo-ui.c

/opt/osdp-conformance/include/open-osdp.h:	../include/open-osdp.h
	mkdir -p /opt/osdp-conformance/include
	cp ../include/open-osdp.h /opt/osdp-conformance/include
	echo really should be a makefile in the include directory
	cp ../include/oo-api.h /opt/osdp-conformance/include

