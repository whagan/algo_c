all: chtbl
CC = gcc
INCLUDE_DIR = ../include
SOURCE_DIR = ../source
OBJS = chtbl_driver.o list.o stack.o 
INST_DIR = /usr/bin

chtbl: $(OBJS)
	   $(CC) -o stack $(OBJS)
stack_driver.o:	stack_driver.o 
				$(CC) -c stack_driver.c -I$(INCLUDE_DIR)
list.o: $(SOURCE_DIR)/list.c 
		$(CC) -c $(SOURCE_DIR)/list.c -I$(INCLUDE_DIR)
stack.o: $(SOURCE_DIR)/stack.c 
		 $(CC) -c $(SOURCE_DIR)/stack.c -I$(INCLUDE_DIR)

clean:
		-@rm -f $(OBJS)

cleanexe:
		-@rm -f stack 

install:	stack 
			@if [ -d $(INST_DIR) ];	\
			then	\
				cp stack $(INST_DIR) &&	\
				chmod a+x $(INST_DIR)/stack &&	\
				chmod og-w $(INST_DIR)/stack &&	\
				echo "stack installed successfully in $(INST_DIR)";	\
			fi
			-@rm -f $(OBJS)
			-@rm -f stack

uninstall:
			@rm -f $(INST_DIR)/stack 
			@echo "stack succesfully uninstalled from $(INST_DIR)"
			
ready:
			@sed -i -n "/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p" ../source/stack.c
			@sed -i -n "/^$$\|^#include\|^#endif\|_H$$\|*$$\|\/$$/p" ../include/stack.h