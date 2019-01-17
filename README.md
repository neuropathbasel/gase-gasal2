# gase-gasal2
GASE/BWA-MEM seed-extension accelerated with GASAL2 

Compile GASAL2 with the following commands in gasal2 directory:
$  ./configure.sh /usr/local/cuda
$   make GPU_SM_ARCH=sm_35 MAX_SEQ_LEN=300 N_CODE=4 N_PENALTY=1

Compile GASE/BWA-MEM with:
$ make

Tested with very large 150-bp paired-end FASTQ files. Works perfectly. Not checked with Valgrind.

