# BMXNet Installation on Windows

This document describes the build and compilation process of [BMXNet](https://gitlab.hpi.de/joseph.bethge/bmxnet). As well as adding the BMXNet Python binding. It is based on those three sources:

1. BMXNet's Readme: [Build the MXNet Python Binding](https://gitlab.hpi.de/joseph.bethge/bmxnet#build-the-mxnet-python-binding)
2. MXNet's Windows Setup: [Build from Source](http://mxnet.incubator.apache.org/install/windows_setup.html#build-from-source)
3. MXNet's Build/Install Instructions: [Verify MXNet with Python](https://github.com/apache/incubator-mxnet/blob/master/MKLDNN_README.md#verify-mxnet-with-python)

## Install Visual Studio 

- Get the [Visual Studio Community Edition 2017](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15).

- During the setup, choose to install the **VC++ 2017 version 15.4 v14.11 toolset**.

- After finishing the installation, modify the version by executing:

  ```bash
  "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat" -vcvars_ver=14.11
  ```

## Install CMake
- Download and install [CMake](https://cmake.org/download), version 3.12.2 (tested) or higher

## Install OpenCV
- Download [OpenVC](https://sourceforge.net/projects/opencvlibrary/files/opencv-win/3.4.1/opencv-3.4.1-vc14_vc15.exe/download) 
- Extract the files to ``C:\utils\opencv`` 
- Define an environment variable using the command line:  ``set OpenCV_DIR=C:\utils\opencv\build`` 

## Install OpenBLAS
- Download [OpenBlas](https://sourceforge.net/projects/openblas/files/v0.2.19/OpenBLAS-v0.2.19-Win64-int32.zip/download) 
- Move all extracted files, including the directories _include_ and _lib_, to ``C:\utils\OpenBLAS``
- Define a environment variable using the command line: ``set OpenBLAS_HOME=C:\utils\OpenBLAS``

## Install CUDA
→ not required if no CUDA-compatible GPU is present

## Install cuDNN
→ not required if no CUDA-compatible GPU is present

## Install git
→ not required if already installed


## Clone the repository
```bash
cd C:\
git clone git@gitlab.hpi.de:joseph.bethge/bmxnet.git --recursive
```

## Build BMXNet
First, create a build directory:
```mkdir C:\bmxnet\build
mkdir C:\bmxnet\build
cd C:\bmxnet\build
```

Thereafter, build BMXNet by running:
```bash
cmake -G "Visual Studio 15 2017 Win64" -T cuda=9.2,host=x64 -DUSE_CUDA=0 -DUSE_CUDNN=0 -DUSE_NVRTC=0 -DUSE_OPENCV=1 -DUSE_OPENMP=1 -DUSE_BLAS=open -DUSE_LAPACK=1 -DUSE_DIST_KVSTORE=0 "C:\bmxnet" 
```

Take a quick look on the output. It should indicate that OpenBLAS and OpenCV were found.

## Compile BMXNet
The process of compiling BMXNet can take a long time (> 30 minutes), depending on your system's performance. For compiling BMXNet run: 


```
msbuild mxnet.sln /p:Configuration=Release;Platform=x64 /maxcpucount
```

The expected output should look like this:

	Build succeeded.
	
	[...]
	
	6 Warning(s)
	0 Error(s)
	
	Time Elapsed 00:21:51.44


## Set Up the Conda environment 
Assuming [Anaconda](https://www.anaconda.com/download/) is already installed on your system, run ``conda create -n bmxnet python=3`` in the Anaconda command prompt (see windows start menu).

Thereafter, activate the recently created environment: ``conda activate bmxnet``.

Lastly, install all required packages by running:

```
pip install numpy scipy matplotlib ipython jupyter pandas sympy nose cpplint==1.3.0 pylint==2.1.1 "numpy<=1.15.2,>=1.8.2" nose-timer "requests<2.19.0,>=2.18.4" h5py==2.8.0 boto3
```

## Install additional files
- Download [mingw64_dll.zip](https://sourceforge.net/projects/openblas/files/v0.2.12/mingw64_dll.zip/download), unzip and copy the libraries (.dll files), which OpenBLAS depends on, to ``C:\common``.
- Add the folder ``C:\common`` to the environment variable _Path_.

## Add the python binding
At last, it is required to install the Python binding:
```
# Assuming you are in root mxnet source code folder
cd python  
python setup.py install
```

## Validate the installation
```
>>> import mxnet as mx
>>> a = mx.nd.ones((2, 3))
>>> b = a * 2 + 1
>>> b.asnumpy()
array([[ 3.,  3.,  3.],[ 3.,  3.,  3.]], dtype=float32)  <--- expected Output
```



## Troubleshooting

### Specified module could not be found
If importing the library in python throws an error:
```
>>> import mxnet
OSError: [WinError 126] The specified module could not be found
```
Probably one of the dependent libraries is not within your *Path*. Check using the CMD, that all of the following DLLs can be found:
- mkldnn.dll

- libopenblas.dll

- opencv_world341.dll

- mklml.dll

- KERNEL32.dll

- VCOMP140.DLL

Use `where <dll-name>`, e.g. `where mkldnn.dll`. If it is within the path, it should show its path, e.g.: 
```
C:\bmxnet> where mkldnn.dll
-> C:\bmxnet\build\3rdparty\mkldnn\src\Release\mkldnn.dll
```

If any DLL cannot be found, search within the folders `C:\bmxnet` and `C:\utils` for it and add the folder, where it is located in, to the path. After adding it to the path, it might be necessary to close and reopen the CMD. Recheck to verify that the DLL can now be found.

### Compiler is out of heap space

```
D:\bmxnet\src\operator\tensor\elemwise_binary_broadcast_op_logic.cc : fatal error C1002: compiler is out of heap space in pass 2 [D:\bmxnet\build\mxnet.vcxproj]
cl : Command line error D8040: error creating or communicating with child process [D:\bmxnet\build\mxnet.vcxproj]
    
164 Warning(s)
4 Error(s)
```

**Solution**: Rerun with less background processes running. A machine with at least 8 GByte RAM is recommended.



