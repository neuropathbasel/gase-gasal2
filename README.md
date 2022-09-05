# gase-gasal2
GASE/BWA-MEM seed-extension accelerated with GASAL2 

Fixed some syntactic issues that were not compatible with ubuntu 18.04.6 in Sept. 2022 (gcc issues). This has only been tested on x86_64.

Install requirements, if not already present:
```
sudo apt install build-essential git libboost-all-dev
```

Clone the repository
```
git clone https://github.com/neuropathbasel/gase-gasal2
```

Compile GASAL2 with the following commands in gasal2 directory:

E.g. for NVIDIA RTX2070 sm_75; tested with cuda-11.4, if a specific cuda version should be employed, use e.g. `/usr/local/cuda-11.4`. Different cuda versions can be installed from the nividia cuda ubuntu developer repo.

```
cd gase-gasal2/gasal2
./configure.sh /usr/local/cuda
make GPU_SM_ARCH=sm_75 MAX_SEQ_LEN=300 N_CODE=4 N_PENALTY=1
```
Fixed some variable naming issues according to https://stackoverflow.com/questions/67013966/error-aligned-was-not-declared-in-this-scope-and-error-expected-before

Replaced all `__aligned__` with `aligned_a`.

Compile GASE/BWA-MEM with:
```
cd ..
make
```
