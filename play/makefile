# Global Setup
TARGET = play
CC = g++ 

# Options
LIBS:= 

IDIR = ./include
_INCLUDE = simdjson.h
INCLUDE = $(patsubst %,$(IDIR)/%,$(_INCLUDE))
# INCLUDE = ./include/hellomake.h	
SDIR= ./srce
_SRCE = quickstart.cpp simdjson.cpp 
SRCE = $(patsubst %,$(SDIR)/%,$(_SRCE))
# SRCE = ./srce/hellomake.c ./srce/hellofunc.c
ODIR= ./obj
_OBJ = quickstart.o simdjson.o  
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))

# https://stackoverflow.com/questions/577006/makefiles-on-windows-with-g-linking-a-library
IEXT=-I"D:/Reference/simdjson/include" -I"D:\Reference\simdjson\singleheader" -I"D:\Reference\simdjson\src"

# Compile
CFLAGS := -I$(IDIR) ${IEXT}
$(ODIR)/%.o: $(SDIR)/%.cpp $(INCLUDE)
	$(CC) -c -o $@ $< $(CFLAGS)

# Link
$(TARGET): $(OBJ)
	$(CC) -o $@ $^ $(LIBS)

# Make Functions
.PHONY: clean
# this rule keeps make from doing something with a file named clean

clean:
	rm -f $(ODIR)/*.o *~ core $(IDIR)/*~ *.exe

show:
	@echo INCLUDE = $(INCLUDE)
	@echo SRCE = $(SRCE)
	@echo OBJ = $(OBJ)
	@echo OPTIONS = $(OPTIONS)
	@echo $(shell ls)