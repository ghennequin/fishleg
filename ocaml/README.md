To compile the experiments:

```sh
dune build src/dln_exact.exe
dune build src/faces.exe
dune build src/mnist.exe
```

To run the experiments:

```sh
export OMP_NUM_THREADS=8
export OCAMLRUNPARAM=s=32M,i=128M,o=100

mpirun -np 10 _build/default/src/dln_exact.exe -d your_results_dir/dln -algo { sgdm | adam | fl }
mpirun -np 10 _build/default/src/faces.exe -d you_results_dir/faces -algo { sgdm | adam | fl }
mpirun -np 10 _build/default/src/mnist.exe -d you_results_dir/mnist -algo { sgdm | adam | fl }
```
