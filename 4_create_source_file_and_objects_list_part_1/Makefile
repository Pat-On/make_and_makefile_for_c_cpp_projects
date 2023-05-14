###############
## VARIABLES ##
###############


# mnake -p
# make build CXX_STANDARD=c++14


# Note: Variables can only be strings
# Note: Single or double quotes for variables names or values have no meaning to Make




# CC: Program for compiling C programs; default cc
# CXX: program for compiling C++ programs; default g++

# CFLAGS: Extra Flags to give to the C compiler
# CXXFLAGS: Extra flags to give to the C++ compiler

# CPPFLAGS: Extra flags to give to the C preprocessor
# LDFAGS: Extra flags to give to the linker


DEBUG = 1 # if 0 realese mode
EXECUTABLE_NAME = main

CXX_STANDARD = c++17
CXX_WARNINGS = -Wall -Wextra -Wpedantic
CC = gcc
CXX = g++

# warnings
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)

# dependencies
# LDFLAGS = -lmath
LDFAGS = 


ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3 
endif


COMPILER_CALL = $(CXX) $(CXXFLAGS) 

CXX_OBJECTS = my_lib.o main.o



execute:
	./main

# buildObj:
# g++ main.cc -c main.o
# g++ my_lib.cc -c my_lib.o
# combining two objects
	# g++ main.o my_lib.0 -o main

build: $(CXX_OBJECTS)
	echo $(COMPILER_CALL)
# g++ main.o my_lib.o -o main
	$(COMPILER_CALL) $(CXX_OBJECTS) $(LDFLAGS) -o $(EXECUTABLE_NAME)
	
main.o:
# g++ main.cc -c main.o
	$(COMPILER_CALL) main.cc -c main.o

my_lib.o:
# g++ my_lib.cc -c my_lib.o
	$(COMPILER_CALL) my_lib.cc -c my_lib.o

# Clean is often used as a targety that removes the output of other targets
clean:
	rm -f main
	rm -f *.o



############################

######		PATTERNS	#####

############################

# $@: the file name of the target
# $<: the name of the first ependency
# $^: the names of all prerequistities
%.o: %.cc # 'template' - define once
	$(CXX_COMPILER_CALL) -c $< -o $@

# %.o: %.cpp # 'template' - define once
# 	$(CXX_COMPILER_CALL) -c $< -o $@

# %.o: %.cxx # 'template' - define once
# 	$(CXX_COMPILER_CALL) -c $< -o $@

# explanation
# main.o: main.cc
# 	$(CXX_COMPILER_CALL) -c $< -o $@