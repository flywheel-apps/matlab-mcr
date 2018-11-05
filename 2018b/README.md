## flywheel/matlab-mcr:v95

Matlab (C) Runtime for MatlabR2018b (v.9.5). For more info see [Matlab's website](http://www.mathworks.com/products/compiler/mcr/).

This container provides an environment for the execution of Stand-Alone Matlab executables built with Matlab (C) 2018b, such as those created using Matlab's 'deploytool'.

### Build ###
```
    docker build --no_cache -t flywheel/matlab-mcr:v95 .
```

### Example Usage ###
To run a Matlab Stand-Alone executable (MSAE) you can do something like the following:
```
    docker run --rm -ti \
        -v </path/to/MSAE/parent/folder>:/execute \
        flywheel/matlab-mcr:v95 \
        /execute/<name of your MSAE> [<any input arguments>]
```

* Note that you are mounting the directory which contains your MSAE in the container at ```/execute``` and executing that file within the container by providing the full path following the name of the container (```flywheel/matlab-mcr:v95```).
* Input arguments to your MSAE are provided at the end of the ```docker run``` command. Remember that if those inputs are files or other resources, those resources must also be mounted in the container and the full path to them (in the container) must be provided.
