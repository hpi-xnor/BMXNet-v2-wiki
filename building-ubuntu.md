# BMXNet Installation on Ubuntu

Here is a guide which helps us:
```bash
# clone the repository 
# important: recursively - with all submodules
git clone --recursive https://github.com/hpi-xnor/BMXNet-v2.git

# install build tools and git
sudo apt-get update && sudo apt-get install build-essential git

# install and build gcc
# skipped as already gcc 5.5.0 installed (required: >= gcc 4.8.5)

# install the OpenBLAS library
sudo apt-get install libatlas-base-dev libopenblas-dev

# install OpenCV
sudo apt-get install libopencv-dev 

# install CMake
# required as current installed version was 3.5.1
mkdir -p ~/utils
wget https://cmake.org/files/v3.12/cmake-3.12.3-Linux-x86_64.tar.gz
tar -zxvf cmake-3.12.3-Linux-x86_64.tar.gz
alias cmake="cmake-3.12.3-Linux-x86_64/bin/cmake"
rm cmake-3.12.3-Linux-x86_64.tar.gz

# install CUDA for nVidia GPU
# not required as 
#   '/home/midl18t2/utils/cuda-samples-9.0/1_Utilities/deviceQuery'
# shows that CUDA Driver 10.0 is already installed

# install CUDNN
# not required as 
#   'cat /usr/include/x86_64-linux-gnu/cudnn_v7.h | grep CUDNN_MAJOR -A 2'
# shows that CUDNN 7.3.1 is installed

# test CUDNN
# running './mnistCUDNN' in '/home/midl18t2/utils/cudnn-samples-v7'
# led to successful classification

# define environment variables
# (see https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#environment-setup)
export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64\
                         ${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

# build the project
mkdir build && cd build
cmake .. -G Ninja
ninja

# install python3 and pip3, if not present
sudo apt-get install -y python3-dev virtualenv
wget -nv https://bootstrap.pypa.io/get-pip.py
python3 get-pip.py

# create a virtualenv
# because we cannot install packages on machines due to missing permissions
# first, check installed python version
ls /usr/bin/python*
# create virtualenv
mkdir -p ~/venvs/bmxnet
virtualenv --python=/usr/bin/python3.6 ~/venvs/bmxnet

# activate virtualenv
cd ~/venvs/bmxnet/bin
source activate 

# install BMXNet python binding
cd ~/bmxnet/python
pip install -e .

# verify that installation was successful
# (see https://mxnet.incubator.apache.org/install/validate_mxnet.html#python)
python # start the Python REPL
import mxnet as mx
a = mx.nd.ones((2, 3))
b = a * 2 + 1
b.asnumpy()
# expected output
array([[ 3.,  3.,  3.],
[ 3., 3., 3.]], dtype=float32)
```
