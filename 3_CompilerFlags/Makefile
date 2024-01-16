#TARGETS

#target: prerequisites
#	commands

# CC: Program for compiling C programs; default cc
# CXX: Program for compiling C++ programs; default g++
# CFLAGS: Extra flags to give to the C compiler
# CXXFLAGS: Extra flags to give to the C++ compiler
# CPPFLAGS: Extra flags to give to the C preprocessor
# LDFLAGS: Extra flags to give to the linker

DEBUG = 1
EXECUTABLE_NAME = main
CXX_STANDARD = c++17
CXX_WARNING = -Wall -Wextra -Wpedantic
CC = gcc
CXX = g++
CXXFLAGS = $(CXX_WARNING) -std=$(CXX_STANDARD)
LDFLAGS = 

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3
endif

COMPILER_CALL = $(CXX) $(CXXFLAGS)

build: my_lib.o main.o
	$(COMPILER_CALL) main.o my_lib.o -o $(EXECUTABLE_NAME)

main.o:
	$(COMPILER_CALL) main.cpp -c

my_lib.o:
	$(COMPILER_CALL) my_lib.cpp -c

run:
	./main

clean:
	rm -f *.o
	rm -f main