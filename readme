# Test Case

## Development and Institutional Context

This test case was developed by Mehrdad Kazemi under the supervision of  
Prof. Dr.-Ing. habil. Nikolai Kornev at:

Universität Rostock  
Fakultät für Maschinenbau und Schiffstechnik  
Lehrstuhl für Modellierung und Simulation  
Albert-Einstein-Str. 2  
18059 Rostock, Germany  

---

## Running the Case

Before running, set the desired options inside `Allrun`:

```bash
PARALLEL_RUN=true    # true for parallel run, false for serial run
nSubDomains=10       # number of processor subdomains for parallel run

Then execute:

chmod +x All*
./Allrun

The script automatically checks whether the mesh exists. If constant/polyMesh is not present, it attempts to extract or copy the mesh from one of the following locations:

mesh/polyMesh.tar.gz
mesh/polyMesh.zip
mesh/polyMesh
Serial Mode

If

PARALLEL_RUN=false

the solver is executed directly in serial mode.

Parallel Mode

If

PARALLEL_RUN=true

the script performs the following steps automatically:

decomposePar
mpirun -np nSubDomains <solver> -parallel
reconstructPar
Cleaning the Case

To remove generated results and reset the case, execute:

./Allclean

This removes generated time directories, processor directories, and post-processing output.

Notes

Before running the case, ensure that the mesh archive or mesh folder is available. The recommended mesh file is:

mesh/polyMesh.zip

Solver settings can be modified in:

system/
constant/

Initial and boundary fields are stored in:

0.orig/
Post-Processing

Post-processing scripts are provided in:

Python_postProcessing_code

To run the post-processing workflow, first enter the folder:

cd Python_postProcessing_code

Then execute:

chmod +x AllrunPostProcesscodes.sh
./AllrunPostProcesscodes.sh

The post-processing scripts require Python 3.12 or a compatible Python 3 environment with the required packages installed.
