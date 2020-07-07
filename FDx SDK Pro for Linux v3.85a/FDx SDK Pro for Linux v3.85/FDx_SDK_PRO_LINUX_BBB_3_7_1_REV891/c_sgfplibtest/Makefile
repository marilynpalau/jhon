#*************************************************************
#*
#* Author :      SecuGen Corporation
#* Description : C SGFPLibTest Makefile
#* Copyright(c): 2009 SecuGen Corporation, All rights reserved
#* date        person   comments
#* ======================================================
#* 12/10/2009  driley   initial release
#*
#*************************************************************
PORT = bbb
CFLAGS = -D__UNIXLINUX
CC=gcc
INCPATH = -I./ -I../include
LIBS =  -L../lib/$(PORT)

OBJS=	main.o 

SRCS=	main.c 

TARGET = ../bin/$(PORT)/c_sgfplibtest
FDU03_TARGET = ../bin/$(PORT)/c_sgfplibtest_fdu03
FDU04_TARGET = ../bin/$(PORT)/c_sgfplibtest_fdu04
FDU05_TARGET = ../bin/$(PORT)/c_sgfplibtest_fdu05

all : $(FDU05_TARGET) $(FDU04_TARGET) $(FDU03_TARGET)

$(FDU05_TARGET) : $(OBJS)
	$(CC) $(CFLAGS) -lstdc++ -lusb -lpthread -lsgfpamx -lsgfdu05 -lsgfplib -o $@ $(OBJS) $(LIBS)
$(FDU04_TARGET) : $(OBJS)
	$(CC) $(CFLAGS) -lstdc++ -lusb -lpthread -lsgfpamx -lsgfdu04 -lsgfplib -o $@ $(OBJS) $(LIBS)
$(FDU03_TARGET) : $(OBJS)
	$(CC) $(CFLAGS) -lstdc++ -lusb -lpthread -lsgfpamx -lsgfdu03 -lsgfplib -o $@ $(OBJS) $(LIBS)

.c.o :
	$(CC) $(CFLAGS) $(INCPATH) -c $<

dep :
	gccmakedep $(INCPATH) $(SRCS)

clean :
	rm -rf *.raw *.min $(OBJS) $(TARGET) core
	rm -rf $(PORT)
	mkdir $(PORT)

