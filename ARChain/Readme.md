For the sharing of ARChain input and output files.  Code by Seppo Mikkola, see the repo in https://github.com/nbodyx/ARChain .  It performs 3.5 Post-Newtonian equations of motion for N-bodies and handles regularization of close approaches using Algorithmic Regularization.

I compile with gfortran from gcc version  9.2.1 20190827 (Red Hat 9.2.1-1) (GCC).  I have also compiled with gcc 4.8 fine.  Compile command is:

gfortran -o AR-CHAIN AR-CHAIN.f

and run with the command (to grab wall clock times and standard output)

echo "" >> time.out ; date >> time.out; AR-CHAIN < MYINPUT.in |tee MYINPUT.stdout; date >> time.out

and if it has the filename in the \*.in file, it creates MYINPUT.out along with many other \*.dat files.
