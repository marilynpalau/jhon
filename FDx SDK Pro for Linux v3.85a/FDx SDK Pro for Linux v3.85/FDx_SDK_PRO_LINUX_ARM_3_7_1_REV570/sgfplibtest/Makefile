#*************************************************************
#*
#* Author :      SecuGen Corporation
#* Description : FPLibTest Makefile
#* Copyright(c): 2009 SecuGen Corporation, All rights reserved
#* date        person   comments
#* ======================================================
#* 12/10/2009  driley   initial release
#*
#*************************************************************

PORT = arm12
CFLAGS = -D__cplusplus -Wall -O
CPP=/opt/arm-marvell-linux-gnueabi/bin/arm-marvell-linux-gnueabi-g++
CC=/opt/arm-marvell-linux-gnueabi/bin/arm-marvell-linux-gnueabi-gcc
INCPATH = -I./ -I../include
LIBS =  -L../lib/$(PORT)

OBJS=	main.o 

SRCS=	main.cpp 

FDU03_TARGET = ../bin/$(PORT)/sgfplibtest_fdu03
FDU04_TARGET = ../bin/$(PORT)/sgfplibtest_fdu04
FDU05_TARGET = ../bin/$(PORT)/sgfplibtest_fdu05

all : $(FDU05_TARGET) $(FDU04_TARGET) $(FDU03_TARGET)

$(FDU05_TARGET) : $(OBJS)
	$(CPP) /opt/arm-marvell-linux-gnueabi/arm-marvell-linux-gnueabi/libc/usr/lib/libusb.so -lpthread -lsgfpamx -lsgfdu05 -lsgfplib -o $@ $(OBJS) $(LIBS)

$(FDU04_TARGET) : $(OBJS)
	$(CPP) /opt/arm-marvell-linux-gnueabi/arm-marvell-linux-gnueabi/libc/usr/lib/libusb.so -lpthread -lsgfpamx -lsgfdu04 -lsgfplib -o $@ $(OBJS) $(LIBS)

$(FDU03_TARGET) : $(OBJS)
	$(CPP) /opt/arm-marvell-linux-gnueabi/arm-marvell-linux-gnueabi/libc/usr/lib/libusb.so  -lpthread -lsgfpamx -lsgfdu03 -lsgfplib -o $@ $(OBJS) $(LIBS)

.cc.o :
	$(CPP) $(FLAGS) $(INCPATH) -c $<

.c.o :
	$(CPP) $(FLAGS) $(INCPATH) -c $<

.cpp.o :
	$(CPP) $(FLAGS) $(INCPATH) -c $<

dep :
	gccmakedep $(INCPATH) $(SRCS)

clean :
	rm -rf *.raw *.min $(OBJS) $(TARGET) core
	rm -rf $(PORT)
	mkdir $(PORT)

