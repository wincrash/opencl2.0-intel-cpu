# opencl2.0-intel-cpu

A Docker image with the
[Intel OpenCL 2.0 CPU Runtime 16.1.1](https://software.intel.com/en-us/articles/opencl-drivers#latest_CPU_runtime)
and OpenCL 2.0 header files. Images with header files from Intel and the Khronos Group are available.

This image has `OCL_INC` and `OCL_LIB` environment variables set to the OpenCL include and library directories, respectively.
`LD_LIBRARY_PATH` is also set to include `OCL_LIB`.

# Using from Docker Hub

For the Intel headers:

    docker run -it cwpearson/opencl2.0-intel-cpu:latest bash -c clinfo

For the Khronos Group headers:

    docker run -it cwpearson/opencl2.0-intel-cpu:khronos-headers bash -c clinfo

You should see a dump of information about the OpenCL capabilities of your system.

# Building for Yourself
Depending on which Docker file you'd like to build.

    docker build -t your_tag_here -f Dockerfile.intel_headers
    docker build -t your_tag_here -f Dockerfile.khronos_headers