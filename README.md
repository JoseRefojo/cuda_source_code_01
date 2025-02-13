======================================================================================

GPU programming for HPC, source code 01



addVectors           - basic hello world style program

makefileCpp          - shows how to add cuda code to your already existing c++ code (without using include on the main, but getting a warning)

makefileCppNoWarning - shows how to add cuda code to your already existing c++ code (using include on the main, so you do not get a warning)

makefileExternC      - shows how to add cuda code to your already existing c code 

mpiHelloWorld        - shows how to add cuda code to your already existing mpi code 

openMPHelloWorld     - shows how to add cuda code to your already existing OpenMP code 





Cuda Bashrc set up

Edit your .bashrc in your home folder, and add these two lines (update the numerical values of the cuda sdk to the version that is installed):

How to add the cuda library paths:

export PATH=$PATH:/usr/local/cuda-12.6/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:"/usr/local/cuda-12.6/lib64"

You can test if things are working by running "nvcc" or "nvvp" (you will have to ss -X or -Y for nvvp to be able to open a window, though).

======================================================================================
