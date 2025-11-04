## Installation

There are three ways to install svZeroDSolver:

1. Download an installer from [SimTK Simvascular Downloads](https://simtk.org/frs/?group_id=188). This will download an executable based on the most recent release.

However, in order to have access to the most up-to-date code, it is recommended to install directly from the github source code using one of the following options:
2. Install using pip. This is the recommended method for using the Python API.
3. Build using CMake. This is the recommended method for using the C++ interface. 

Instructions on the pip and CMake installation methods are below.

### Using pip

For a pip installation, simply run the following command
(cloning of the repository is not required):

```bash
pip install git+https://github.com/simvascular/svZeroDSolver.git
```

If you would like to clone the repository in order to develop or inspect the source code, you can do the following:

```bash
git clone https://github.com/simvascular/svZeroDSolver.git
cd svZeroDSolver
pip install -e .
```

<br/>
<details>
  <summary><mark><b>Note: installing via pip on HPC cluster</b></mark></summary>

When installing the svzerodsolver via pip on an HPC cluster, ensure that you are on an interactive node with at least 8GB of memory. For example, on the Sherlock HPC cluster (where the default memory for an interactive node is 4GB) you would request a node with adequate memory using
```bash
sdev -m 8GB
```
</details>
<br/>

### Using CMake

If you want to build svZeroDSolver manually from source, clone the repository
and run the following commands from the top directory of the svZeroDSolver project:

```bash
mkdir Release
cd Release
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake --build .
```
<br/>
<details>
  <summary><mark><b>Note: Building on Sherlock for Stanford users</b></mark></summary>

```bash
module load cmake/3.23.1 gcc/14.2.0 binutils/2.38
mkdir Release
cd Release
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_COMPILER=/share/software/user/open/gcc/14.2.0/bin/g++ -DCMAKE_C_COMPILER=/share/software/user/open/gcc/14.2.0/bin/gcc ..
cmake --build .
```
</details>
<br/>
