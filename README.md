# askapsoft-container
Singularity recipe file to build a Singularity askapsoft container

## **How to**  
1. Build first base container with all dependencies and store it to image name `askapsoft_base.simg`: 
     
       singularity build askap_base.simg base/Singularity.xenial     
            
   This container will install all dependencies and modules needed to build askapsoft on Ubuntu 16.04 (xenial). Installed software include:
   - build tools (e.g. gcc, python, etc.)
   - system libraries to build following libraries
   - openmpi
   - boost
   - casacore
   - aoflagger
   - casa
   
   You can edit the recipe file to change the software versions being installed.
   
2. Build askapsoft container from local base container image built in previous step and store it to image name `askapsoft.simg`. Make sure that base image path is correct at the beginning of askapsoft/Singularity.xenial recipe file): 

       singularity build askapsoft.sim askapsoft/Singularity.xenial           
       
