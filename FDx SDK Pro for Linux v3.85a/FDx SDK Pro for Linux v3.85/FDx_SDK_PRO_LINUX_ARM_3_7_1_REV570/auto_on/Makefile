#*************************************************************
#*
#* Author :      SecuGen Corporation
#* Description : AUTO ON Makefile
#* Copyright(c): 2009 SecuGen Corporation, All rights reserved
#* date        person   comments
#* ======================================================
#* 12/10/2009  driley   initial release
#*
#*************************************************************

PORT = arm12
CFLAGS = -D__cplusplus -Wall -O
CPP=/opt/arm-marvell-linux-gnueabi/bin/arm-marvell-linux-gnueabi-g++
INCPATH = -I./ -I../include
LIBS =  -L../lib/$(PORT) 

FDU03_TARGET = ../bin/$(PORT)/auto_on_fdu03
FDU04_TARGET = ../bin/$(PORT)/auto_on_fdu04
FDU05_TARGET = ../bin/$(PORT)/auto_on_fdu05

all : $(FDU05_TARGET) $(FDU04_TARGET) $(FDU03_TARGET)

$(FDU05_TARGET) : $(OBJS)
	rm -rf $(PORT)/main.o
	$(CPP) $(FLAGS) $(INCPATH) -D_FDU05 /opt/arm-marvell-linux-gnueabi/arm-marvell-linux-gnueabi/libc/usr/lib/libusb.so -lpthread -lsgfpamx -lsgfdu05 -lsgfplib -o $@ main.cpp $(LIBS)

$(FDU04_TARGET) : $(OBJS)
	rm -rf $(PORT)/main.o
	$(CPP) $(FLAGS) $(INCPATH) -D_FDU04 /opt/arm-marvell-linux-gnueabi/arm-marvell-linux-gnueabi/libc/usr/lib/libusb.so -lpthread -lsgfpamx -lsgfdu04 -lsgfplib -o $@ main.cpp $(LIBS)

$(FDU03_TARGET) : $(OBJS)
	rm -rf $(PORT)/main.o
	$(CPP) $(FLAGS) $(INCPATH) -D_FDU03 /opt/arm-marvell-linux-gnueabi/arm-marvell-linux-gnueabi/libc/usr/lib/libusb.so -lpthread -lsgfpamx -lsgfdu03 -lsgfplib -o $@ main.cpp $(LIBS)

clean :
	rm -rf *.raw $(OBJS) $(FDU03_TARGET) $(FDU04_TARGET) core
	rm -rf $(PORT)
	mkdir $(PORT)

