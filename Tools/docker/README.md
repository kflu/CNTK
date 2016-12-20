# CNTK Dockerfiles

The Dockerfiles provided here can be used to build CNTK on machines with only CPU, or with GPU with or without 1bit-SGD.
If you plan to use the 1bit-SGD version, please make sure you understand the 
[license difference between CNTK and 1bit-SGD](https://github.com/Microsoft/CNTK/wiki/Enabling-1bit-SGD).

See also [this page](https://github.com/Microsoft/CNTK/wiki/CNTK-Docker-Containers) 
that provides general instructions on getting things working with Docker.

# NOTE

`docker build` needs to be run on machines with multiple CPU. Otherwise OpenBlas compilation
will fail as USE_THREAD=0 and USE_OPENMPL conflict.

Also when compiling CNTK one needs to specify the python versions to build with
`--with-py-versions`, as python27 is by default included, but in previous steps
anaconda wasn't built for python27 (only for python 34), so we need to explicitly
exclude python 27 by specifying `--with-py-versions=34`.
