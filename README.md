# Test Case

This repository contains the OpenFOAM test case used in the manuscript.  
The case was developed by Mehrdad Kazemi under the supervision of Prof. Dr.-Ing. habil. Nikolai Kornev at the University of Rostock, Chair of Modelling and Simulation.

## Run the Case

Edit the run options in `Allrun` if needed:

    PARALLEL_RUN=true
    nSubDomains=10

Then run:

    chmod +x All*
    ./Allrun

If `constant/polyMesh` is not available, the script automatically extracts or copies the mesh from one of the following locations:

    mesh/polyMesh.tar.gz
    mesh/polyMesh.zip
    mesh/polyMesh

In serial mode (`PARALLEL_RUN=false`), the solver is run directly.  
In parallel mode (`PARALLEL_RUN=true`), the script runs `decomposePar`, executes the solver with MPI, and reconstructs the results.

## Clean the Case

To remove generated results and reset the case:

    ./Allclean

## Post-Processing

Post-processing scripts are provided in:

    Python_postProcessing_code

To run them:

    cd Python_postProcessing_code
    chmod +x AllrunPostProcesscodes.sh
    ./AllrunPostProcesscodes.sh

Python 3.12, or a compatible Python 3 environment, is recommended.

## Notes

- Initial and boundary fields are stored in `0.orig/`.
- Solver settings are stored in `system/` and `constant/`.
- The recommended mesh archive is `mesh/polyMesh.zip`.
