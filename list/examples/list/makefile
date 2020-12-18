all: linklist
CC=gcc
INCLUDE_DIR=../../include
SOURCE_DIR=../../source/
OBJS = list_driver.o list.o 
INST_DIR = /usr/bin


linklist: $(OBJS)
		 $(CC) -o linklist $(OBJS)
list_driver.o:	list_driver.c
				$(CC) -c list_driver.c -I$(INCLUDE_DIR)
list.o: $(SOURCE_DIR)/list.c $(INCLUDE_DIR)/list.h
		$(CC) -c $(SOURCE_DIR)/list.c -I$(INCLUDE_DIR)

clean:
		-@rm -f $(OBJS)

cleanexe:
		-@rm -f linklist

install:	linklist
			@if [ -d $(INST_DIR) ];	\
			then	\
				cp linklist $(INST_DIR) &&	\
				chmod a+x $(INST_DIR)/linklist &&	\
				chmod og-w $(INST_DIR)/linklist &&	\
				echo "linklist installed successfully in $(INST_DIR)";	\
			fi
			-@rm -f $(OBJS)
			-@rm -f linklist

uninstall:
			@rm -f $(INST_DIR)/linklist
			@echo "linklist successfully uninstalled from $(INST_DIR)"

ready:
			@sed -i -n '/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p' ../../source/list.c
			@sed -i -n '/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p' ../../include/list.h