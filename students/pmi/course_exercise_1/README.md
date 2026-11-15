# Makefile has various aspects.

## Variables

- ENV: not mandatory, but a venv shall be useful for visualization through plot_orbits.py.
- INPUT: this is the name of the input file. By default, it will be input.dat.
- IMAGE: name of the image created by the python script


## Commands

- make: this will compile with -fopenmp -O2 by default.
- make plot: this will plot the orbits followed by the particles in output.dat.
- make everything: this one will directly compile, run and plot.
- make clean: actually unlikely to be useful. It will delete everything that was just a requirement for compiling the main program (which is already done by every other command), but is actually useful when an error ocurs.


## Parallelisation

We can assign the number of threads (for example, 4) in case we run directly with make as

- OMP_NUM_THREADS=4 make everything


And we can change flags, to compile without fopenmp (or whatever other purposes) like

- make everything FLAGS="-O2"




# Results

### Run time in seconds

|   n    | 1 Thread | 2 Threads | 4 Threads | 8 Threads |
|--------|----------|-----------|-----------|-----------|
| 1000   | 1.83     | 1.38      | 0.81      | 0.4800    |
| 2000   | 7.34     | 5.54      | 3.24      | 2.4010    |
| 5000   | 26.50    | 22.01     | 14.00     | 9.7450    |
| 10000  | 96.22    | 73.67     | 45.36     | 28.6050   |
