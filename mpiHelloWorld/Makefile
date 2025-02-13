# Makefile
# $< means first dependency of the current target
# $+ means all current dependencies
# $@ means current target

# Variables for the makefile
CC = mpicc
CFLAGS = -Wall -O2  -ffast-math
LDFLAGS = -lm -ffast-math

MPICC      	= nvcc -Xptxas -v 
#MPI_INCLUDES    = /usr/include/x86_64-linux-gnu/mpich/
MPI_INCLUDES    = /usr/include/openmpi

#if [ ! -d "./$(BIN)" ]; then endif


#MPI_LIBS   	= /usr/mpi/intel/mvapich2-1.2p1/lib 
MPI_LIBS   	= /usr/lib/openmpi


check_dir:
	@if [ ! -d "$(MPI_INCLUDES)" ]; then \
		echo "Directory $(MPI_INCLUDES) Was not foung. Please set the MPI_INCLUDES variable to point to the location of mpi.h and then try compiling again"; \
	else \
		echo "Directory $(MPI_INCLUDES) was found, proceeding."; \
	fi

# default target
mpiHelloWorld.exec : mpiHelloWorld.o
	$(MPICC) -L$(MPI_LIBS) -lmpi -o $@ *.o 

%.o : %.cu check_dir
	$(MPICC) -I$(MPI_INCLUDES) -o $@ -c $< 

#cudaMpiHelloWorld.out: cudaMpiHelloWorld.o
#	echo "Makefile - target cudaMpiHelloWorld.out"
#	$(CC) $(LDFLAGS) -o $@ $+

# Those are not necessary
#%.o: %.c
#	$(CC) -c $< $(CFLAGS)

test: mpiHelloWorld.exec
	./mpiHelloWorld.exec

#clean
.PHONY: clean
clean:
	rm -f *.o *.exe
