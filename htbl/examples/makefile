all: chtbl 
CC = gcc
INCLUDE_DIR = ../include
SOURCE_DIR = ../source
OBJS = chtbl_driver.o chtbl.o list.o 
INST_DIR = /usr/bin

chtbl: 		$(OBJS)
	   		$(CC) $(OBJS) -o chtbl

chtbl_driver.o:	chtbl_driver.c
				$(CC) -c chtbl_driver.c -I$(INCLUDE_DIR)

chtbl.o:		$(SOURCE_DIR)/chtbl.c
				$(CC) -c $(SOURCE_DIR)/chtbl.c -I$(INCLUDE_DIR)

list.o:			$(SOURCE_DIR)/list.c
				$(CC) -c $(SOURCE_DIR)/list.c -I$(INCLUDE_DIR)

clean:
		-@rm -f $(OBJS)

cleanexe:
		-@rm -f chtbl 

install:	chtbl 
			@if [ -d $(INST_DIR) ];	\
			then	\
				cp chtbl $(INST_DIR) &&	\
				chmod a+x $(INST_DIR)/chtbl &&	\
				chmod og-w $(INST_DIR)/chtbl &&	\
				echo "chtbl installed successfully in $(INST_DIR)";	\
			fi
			-@rm -f $(OBJS)
			-@rm -f chtbl

uninstall:
			@rm -f $(INST_DIR)/chtbl 
			@echo "chtbl succesfully uninstalled from $(INST_DIR)"
			
ready:
			@sed -i -n "/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p" ../source/chtbl.c
			@sed -i -n "/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p" ../include/chtbl.h