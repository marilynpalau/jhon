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

PORT = bbb
CFLAGS = -Wall -O
CXX=g++
CC=gcc
INCPATH = -I./ -I../include
LIBS =  -L../lib/$(PORT)

OBJS=	main.o 

SRCS=	main.cpp 

FDU03_TARGET = ../bin/$(PORT)/multidev_fdu03
FDU04_TARGET = ../bin/$(PORT)/multidev_fdu04
FDU05_TARGET = ../bin/$(PORT)/multidev_fdu05

all : $(FDU05_TARGET) $(FDU04_TARGET) $(FDU03_TARGET)

$(FDU05_TARGET) : $(OBJS)
	$(CXX) -o $@ $(OBJS) $(LIBS) -lsgfplib -lsgfpamx -lsgfdu05 -lpthread  -lusb

$(FDU04_TARGET) : $(OBJS)
	$(CXX) -o $@ $(OBJS) $(LIBS) -lsgfplib -lsgfpamx -lsgfdu04 -lpthread  -lusb

$(FDU03_TARGET) : $(OBJS)
	$(CXX) -o $@ $(OBJS) $(LIBS) -lsgfplib -lsgfpamx -lsgfdu03 -lpthread  -lusb

.cc.o :
	$(CXX) $(FLAGS) $(INCPATH) -c $<

.c.o :
	$(CXX) $(FLAGS) $(INCPATH) -c $<

.cpp.o :
	$(CXX) $(FLAGS) $(INCPATH) -c $<

dep :
	gccmakedep $(INCPATH) $(SRCS)

clean :
	rm -rf *.raw *.min $(OBJS) $(FDU04_TARGET) $(FDU03_TARGET)  core
	rm -rf $(PORT)
	mkdir $(PORT)

