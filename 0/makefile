all: nbody.g nbody.i
#nbody.g
#nbody.i
#nbody.cl

nbody.g: nbody.c
	gcc -march=native -mavx512f -Ofast -fopt-info-all=nbody.gcc.optrpt $< -o $@ -lm -fopenmp

#nbody.cl: nbody.c
#clang -march=native -mavx2 -Ofast  $< -o $@ -lm -fopenmp

nbody.i: nbody.c
	icc -xhost -Ofast -qopt--zmm-usage=high $< -o $@ -qopenmp
##-O3 -xHost -qopt-zmm-usage=high
#icc -xhost -Ofast -qopt-report $< -o $@ -qopenmp
#icc -Ofast -mavx2 $< -o $@ -qopenmp
#-qmkl

clean:
	rm -Rf *~ nbody.g nbody.i *.optrpt
#nbody.i 
