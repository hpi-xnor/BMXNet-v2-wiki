# Building

This page contains some essential commands for building the project.
However, please also consult the information in the README of the main project if you are stuck.

## ArchLinux
```bash
git clone --recursive git@gitlab.hpi.de:joseph.bethge/bmxnet.git
mkdir build
cd build
cmake -G Ninja \
   -DCMAKE_BUILD_TYPE=Release \
   -DBLAS=Open \
   -DCUDA_HOST_COMPILER=/usr/bin/gcc-6 \
   -DUSE_GPERFTOOLS=OFF \
   -DCMAKE_CXX_COMPILER=/usr/bin/g++-7 \
   -DCMAKE_C_COMPILER=/usr/bin/gcc-7 \
   ..
ninja -j 8
```

## Ubuntu

See [Building on Ubuntu](building-ubuntu).

## MacOS without OpenMP
- Step 1: Install xCode from [AppStore](https://itunes.apple.com/de/app/xcode/id497799835?mt=12)
- Step 2: Install `ninja` and set it as default build system in cmake
```bash
brew install ninja
```

Turn OpenMP off:
```bash
cmake .. -G Ninja \
-DCMAKE_BUILD_TYPE=Release \
-DUSE_CUDA=FALSE \
-DUSE_OPENCV=FALSE \
-DUSE_OPENMP=FALSE \
-DUSE_GPERFTOOLS=OFF
```

## MacOS with OpenMP
Install CMake >= 3.12.3.
Afterwards this command has worked:
```bash
cmake ../ \
-DCMAKE_BUILD_TYPE=Release \
-DUSE_CUDA=FALSE \
-DUSE_OPENMP=TRUE \
-DUSE_GPERFTOOLS=OFF \
-DCMAKE_C_COMPILER="/usr/local/opt/llvm/bin/clang" \
-DOpenMP_C_LIB_NAMES="omp" \
-DCMAKE_CXX_COMPILER="/usr/local/opt/llvm/bin/clang++" \
-DOpenMP_CXX_LIB_NAMES="omp" \
-DOpenMP_omp_LIBRARY="[/path/to/bmxnet]/build/3rdparty/openmp/runtime/src/libomp.dylib"
```

## Windows
See [Building on Windows](building-windows).
