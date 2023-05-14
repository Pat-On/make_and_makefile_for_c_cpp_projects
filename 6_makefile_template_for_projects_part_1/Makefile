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

INCLUDE_DIR = include
SOURCE_DIR = src
BUILD_DIR = build




CXX_STANDARD = c++17
CXX_WARNINGS = -Wall -Wextra -Wpedantic
CC = gcc
CXX = g++

CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
CPPFLAGS = -I $(INCLUDE_DIR) # I - include dir

LDFAGS = 

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif


CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS) $(CPPFLAGS)
# pattern matching *.cc
CXX_SOURCES = $(wildcard $(SOURCE_DIR)/*.cc)

# pattern substitution
# $(text:pattern=replacement)
CXX_OBJECTS = $(patsubst $(SOURCE_DIR)/%.cc, $(BUILD_DIR)/%.o, $(CXX_SOURCES))

###################
# TARGETS
###################

create:
	mkdir build

build: create $(CXX_OBJECTS)
	$(CXX_COMPILER_CALL) $(CXX_OBJECTS) $(LDFLAGS) -o $(BUILD_DIR)/$(EXECUTABLE_NAME)

execute:
	./$(BUILD_DIR)/$(EXECUTABLE_NAME)

# Clean is often used as a targety that removes the output of other targets
clean:
	rm -f $(BUILD_DIR)/*.o
	rm -f $(BUILD_DIR)/$(EXECUTABLE_NAME)



############################

######		PATTERNS	#####

############################

# $@: the file name of the target
# $<: the name of the first ependency
# $^: the names of all prerequistities
$(BUILD_DIR)/%.o: $(SOURCE_DIR)/%.cc
	$(CXX_COMPILER_CALL) -c $< -o $@
