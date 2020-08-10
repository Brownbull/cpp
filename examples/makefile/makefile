# Global Setup
TARGET = play
CC = g++ 

# Options
LIBS:= 

IDIR = ./include
_INCLUDE = Point.h Rectangle.h
INCLUDE = $(patsubst %,$(IDIR)/%,$(_INCLUDE))
# INCLUDE = ./include/hellomake.h	
SDIR= ./srce
_SRCE = main.cpp Point.cpp Rectangle.cpp 
SRCE = $(patsubst %,$(SDIR)/%,$(_SRCE))
# SRCE = ./srce/hellomake.c ./srce/hellofunc.c
ODIR= ./obj
_OBJ = main.o Point.o Rectangle.o  
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))

# Compile
CFLAGS := -I$(IDIR) 
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