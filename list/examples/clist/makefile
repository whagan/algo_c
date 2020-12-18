all: clinklist
CC=gcc
INCLUDE_DIR=../../include
SOURCE_DIR=../../source/
OBJS = clist_driver.o clist.o 
INST_DIR = /usr/bin


clinklist: $(OBJS)
		 $(CC) -o clinklist $(OBJS)
clist_driver.o:	clist_driver.c
				$(CC) -c clist_driver.c -I$(INCLUDE_DIR)
clist.o: $(SOURCE_DIR)/clist.c $(INCLUDE_DIR)/clist.h
		$(CC) -c $(SOURCE_DIR)/clist.c -I$(INCLUDE_DIR)

clean:
		-@rm -f $(OBJS)

cleanexe:
		-@rm -f clinklist

install:	clinklist
			@if [ -d $(INST_DIR) ];	\
			then	\
				cp clinklist $(INST_DIR) &&	\
				chmod a+x $(INST_DIR)/clinklist &&	\
				chmod og-w $(INST_DIR)/clinklist &&	\
				echo "clinklist installed successfully in $(INST_DIR)";	\
			fi
			-@rm -f $(OBJS)
			-@rm -f clinklist

uninstall:
			@rm -f $(INST_DIR)/clinklist
			@echo "clinklist successfully uninstalled from $(INST_DIR)"

ready:
			@sed -i -n '/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p' ../../source/clist.c
			@sed -i -n '/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p' ../../include/clist.h