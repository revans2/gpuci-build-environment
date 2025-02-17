# gpuci-build-environment

Common build environment used by gpuCI for building RAPIDS

## Usage

### Build Environment Dockerfile

[![Build Status](http://gpuci.gpuopenanalytics.com/buildStatus/icon?job=goai-docker-container-builder)](http://gpuci.gpuopenanalytics.com/job/goai-docker-container-builder/)

Updates pushed to `master` will trigger
[builds](http://gpuci.gpuopenanalytics.com/job/goai-docker-container-builder/) of the Docker
containers used for the [gpuCI service](http://gpuci.gpuopenanalytics.com/)

### Build Scripts

1. Add or modify scripts to `build-scripts/` folder saving file with the name of
the job appended with `.sh`
2. Change the **Execute Shell** step in the Jenkins job to the following:
```
echo -e "\n\n>>>> Cloning build scripts...\n\n"
git clone https://github.com/gpuopenanalytics/gpuci-build-environment.git
bash gpuci-build-environment/build-scripts/${JOB_BASE_NAME}.sh
```
3. Trigger new build after changes are pushed to master to use new scripts
