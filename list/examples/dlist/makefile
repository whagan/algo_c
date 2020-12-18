all: dlinklist
CC=gcc
INCLUDE_DIR=../../include
SOURCE_DIR=../../source/
OBJS = dlist_driver.o dlist.o 
INST_DIR = /usr/bin


dlinklist: $(OBJS)
		 $(CC) -o dlinklist $(OBJS)
dlist_driver.o:	dlist_driver.c
				$(CC) -c dlist_driver.c -I$(INCLUDE_DIR)
dlist.o: $(SOURCE_DIR)/dlist.c $(INCLUDE_DIR)/dlist.h
		$(CC) -c $(SOURCE_DIR)/dlist.c -I$(INCLUDE_DIR)

clean:
		-@rm -f $(OBJS)

cleanexe:
		-@rm -f dlinklist

install:	dlinklist
			@if [ -d $(INST_DIR) ];	\
			then	\
				cp dlinklist $(INST_DIR) &&	\
				chmod a+x $(INST_DIR)/dlinklist &&	\
				chmod og-w $(INST_DIR)/dlinklist &&	\
				echo "dlinklist installed successfully in $(INST_DIR)";	\
			fi
			-@rm -f $(OBJS)
			-@rm -f dlinklist

uninstall:
			@rm -f $(INST_DIR)/dlinklist
			@echo "dlinklist successfully uninstalled from $(INST_DIR)"

ready:
			@sed -i -n '/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p' ../../source/dlist.c
			@sed -i -n '/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p' ../../include/dlist.h