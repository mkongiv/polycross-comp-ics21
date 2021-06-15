Software Artifact for ICS'21 paper: "Tile Size Selection of Affine Programs for GPGPUs using Polyhedral Cross-Compilation".

*Requisites*:

- PoCC v1.5.0: pocc-1.5.0-beta-selfcontained.tar.gz
(PoCC has its own set of dependences, including Automake, GMP, etc).
- IBM Cplex

PoCC can be downloaded from: https://sourceforge.net/projects/pocc/files/1.5/


*Installation steps:*

Install PoCC 1.5:

tar xvzf pocc-1.5.0-beta-selfcontained.tar.gz

mv pocc-1.5.0-beta pocc-gpu-tss

cd pocc-gpu-tss

./install.sh

Next, copy the directory ics21-patches to PoCC's root (pocc-gpu-tss).

Enter ics21-patches and run:

./apply-ics21-patch.sh



*Use:* 
Invoke the Python script gpu-tss.py.
Example: python gpu-tss.py gemm.c V100 2000 vector-mode

The script will print the selected tile sizes.

*Notes:*
- To cite this work:

@inproceedings{10.1145/3447818.3460369,
author = {Abdelaal, Khaled and Kong, Martin},
title = {Tile Size Selection of Affine Programs for GPGPUs Using Polyhedral Cross-Compilation},
year = {2021},
isbn = {9781450383356},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3447818.3460369},
doi = {10.1145/3447818.3460369},
booktitle = {Proceedings of the ACM International Conference on Supercomputing},
pages = {13--26},
numpages = {14},
keywords = {GPGPU, affine transformations, PPCG, polyhedral model, cross-compilation, tile size selection},
location = {Virtual Event, USA},
series = {ICS '21}
}

- Generated C files (\*.atss.\*.c) are only for reference. Please refer to the paper for details.
