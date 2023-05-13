# TARGET - name for certain operations
# Pattern:
# target: prerequisities
# commands


# The comnmands are a series of steps typically to make the target
# need to start with a tab character not space
# the prerequisities are files namers separated by spaces
# these files need to exist before the commands for the target are run


build: # executed if we are going to call 'make' only
	g++ main.cc -o main

execute:
	./main

buildObj:
	g++ main.cc -c main.o
	g++ main.o -o main


# Clean is often used as a targety that removes the output of other targets
clean:
	rm -f main
	rm -f *.o

