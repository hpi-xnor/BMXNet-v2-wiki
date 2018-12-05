Hyperparameters, training graph, tail of training log, and csv with values in the log can be found in details for each model.

## ResNet

### CIFAR10

|Layers|Version|Scaled?|Best Top1 Acc|Best Top5 Acc|Details|
|-|-|-|-|-|-|
|18|v1|no |87.9|99.7|[here](experiment/first_exps/1/details)|

### ImageNet

|Layers|Version|Scaled?|Best Top1 Acc|Best Top5 Acc|Details|Commment|
|-|-|-|-|-|-|-|
|18|v1|no    |(49.2)|(73.3)|[here](experiment/first_exps/0/details)|no LR update|
|18|v1|yes   |51.9|75.5|[here](experiment/first_exps/2/details)||
|18|v2|**no**|53.2|76.5|[here](experiment/first_exps/3/details)||
|18|v2|yes   |49.5|73.4|[here](experiment/mnes/7af1782549bcbfbf343fb6db5960ae57/details)||

## DenseNet

### CIFAR10

|Layers|Growth-Rate|Init-Features|Reduction|Model Size|FP SC|Relu SC|Best Top1 Acc|Best Top5 Acc|Details|
|-|-|-|-|-|-|-|-|-|-|
|21|128|128|1,1.4,1.4|1.4 MB|no |no |87.8|99.5|[here](experiment/mnes/f89a35cd7a63f068884f1c281c56d7cd/details)|
|21|128|128|2,2,2    |      |yes|no |86.4|99.4|[here](experiment/mnes/b62af212784e69f6765d70b142ad8084/details)|
|21|128|128|2,2,2    |      |yes|yes|90.3|99.7|[here](experiment/mnes/cd834dc649d4e4fb26bfadc2250de669/details)|
|21|128|128|1,1.4,1.4|      |no |no |87.6|99.5|[here](experiment/mnes/ffb6ebbb1cc5e32aee8cf33676ae0b3d/details)|

### ImageNet

|Layers|Growth-Rate|Init-Features|Reduction|Model Size|FP SC|Relu SC|Best Top1 Acc|Best Top5 Acc|Details|
|-|-|-|-|-|-|-|-|-|-|
|13|256|64 |1,1.4,1.4  |3.31 MB|no |no |50.2|73.7|[here](experiment/mnes/5310129781ba5634d7c28e3d37a8d290/details)|
|21|128|64 |1,1.4,1.4  |3.39 MB|no |no |52.7|75.7|[here](experiment/mnes/577d491dd030de121ea6e99568bb2fac/details)|
|37| 64|64 |1,1.4,1.4  |3.45 MB|no |no |54.3|77.3|[here](experiment/mnes/9365efc91add2928b231ce33e00de2e0/details)|
|13|256|128|1,1.4,1.4  |       |no |no |51.9|75.2|[here](experiment/mnes/a49e6a978753a591c399cb7007c08985/details)|
|21|128|128|1,1.4,1.4  |       |no |no |54.1|77.1|[here](experiment/mnes/620f2ddcb7f151d11c28b559b87cd5a1/details)|
|21|128|128|1.5,1.4,1.4(+sc)|  |no |no |52.7|76.2|[here](experiment/mnes/f27ba3b3852e9c7636b5fe3fd9a0f438/details)|
|37| 64| 64|2,2,2      |3.08 MB|yes|yes|57.1|80.0|[here](experiment/mnes/7f5528fd2e30840542c149d9373b7e77/details)|
|21|128| 64|2,2,2      |3.03 MB|yes|yes|55.9|78.5|[here](experiment/mnes/aec2305cee8a661a0b6a1cbd37656396/details)|
|21|128|128|2,2,2      |3.48 MB|yes|yes|57.2|79.6|[here](experiment/mnes/6aacfa88063440862a6da6706c7b95d1/details)|
|21|160|128|2,2,2      |4.4  MB|yes|yes|59.3|81.4|[here](experiment/mnes/f98c27ec7159867245059107681baf50/details)|
|21|160|128|2.2,2.2,2.2|3.99 MB|yes|yes|58.6|81.0|[here](experiment/mnes/d61bb1310df93f6ef28b18752d5ac416/details)|

## ResNetE

### CIFAR10

|Layers|Version|Scaled?|FP SC|Pool SC|Approx Sign|Best Top1 Acc|Best Top5 Acc|Details|
|-|-|-|-|-|-|-|-|-|
|18|1|no |no |yes|yes|  84.1  |99.3|[here](experiment/mnes/45c310d5f81dd1ea062e1b348848393f/details)|
|18|1|no |no |yes|no |  85.6  |99.3|[here](experiment/mnes/44db0eb425328a2f8958173346c79005/details)|
|18|1|no |yes|yes|yes|  84.9  |99.3|[here](experiment/mnes/5b75bfeb8d49c2491ef29572c489e369/details)|
|18|1|no |yes|yes|no |  86.1  |99.3|[here](experiment/mnes/555b03684f0df3ea0cf98d4260279f8f/details)|
|18|2|no |no |yes|yes|  84.9  |99.3|[here](experiment/mnes/512c14e19fe4a7dda4f3502b3fd387e3/details)|
|18|2|no |no |yes|no |**87.2**|99.5|[here](experiment/mnes/c997eadfeb1def1a6057c7a01ce1a2ae/details)|
|18|2|no |yes|yes|yes|  86.1  |99.4|[here](experiment/mnes/23854efc0783488b942816162c315ae6/details)|
|18|2|no |yes|yes|no |**87.6**|99.5|[here](experiment/mnes/01686f785a65812514fbd8d723cbb2aa/details)|
|18|1|yes|no |yes|yes|  83.7  |99.2|[here](experiment/mnes/61831fea811d0e7f97c93a735d996f31/details)|
|18|1|yes|no |yes|no |  85.6  |99.3|[here](experiment/mnes/98ba31dd6546e4c1f3bc6f5f43c03947/details)|
|18|1|yes|yes|yes|yes|  83.8  |99.1|[here](experiment/mnes/b6dfc6d92c9620b63b8e2880e5c08fe3/details)|
|18|1|yes|yes|yes|no |  86.1  |99.2|[here](experiment/mnes/ec93eaae3defc92ec1c720a82457c32d/details)|
|18|2|yes|no |yes|yes|  84.2  |99.2|[here](experiment/mnes/861709f7a0cd1909b8e27c03e6a2377d/details)|
|18|2|yes|no |yes|no |  83.6  |99.2|[here](experiment/mnes/3bde3fa195160eb168c5b7384ac165fd/details)|
|18|2|yes|yes|yes|yes|  84.4  |99.3|[here](experiment/mnes/60ef08db9c7b976e75783f0e116bf691/details)|
|18|2|yes|yes|yes|no |  84.7  |99.2|[here](experiment/mnes/c9d781b6ccb2fdbbedddbfb73dcb35da/details)|
|34|1|no |yes|yes|no |  86.2  |99.3|[here](experiment/mnes/5a6ec36f7675fe899ff7574e615fca7a/details)|

### ImageNet

|Layers|Version|Scaled?|FP SC|Pool SC|Approx Sign|Best Top1 Acc|Best Top5 Acc|Details|
|-|-|-|-|-|-|-|-|-|
|18|1|no |no |yes|yes|  54.3  |  77.6  |[here](experiment/mnes/56d3ac46a2ade67323db9e2ddcd300be/details)|
|18|1|no |no |yes|no |  54.4  |  77.5  |[here](experiment/mnes/f3398fb5a606ff35b8bbb0286d862ef3/details)|
|18|1|no |yes|yes|yes|  56.6  |**79.3**|[here](experiment/mnes/276d3c968497c043174958377ab34a35/details)|
|18|1|no |yes|yes|no |**56.7**|  79.2  |[here](experiment/mnes/cbf66df53543ea6cdd8d13c6c0aa4f52/details)|
|18|1|yes|yes|yes|yes|  55.3  |  78.3  |[here](experiment/mnes/205a83b81f9a3cb2c8594118428f2375/details)|
|18|1|yes|yes|yes|no |  55.6  |  78.4  |[here](experiment/mnes/13b07f8791702f96a8da5515bbc3c7f1/details)|
|18|1|yes|no |yes|yes|  53.3  |  76.4  |[here](experiment/mnes/489228e35ce28008e50f8a344288ddb4/details)|
|18|1|yes|no |yes|no |  52.7  |  76.1  |[here](experiment/mnes/f900d8bf2953a40f31f3c5c71cfdb844/details)|
|18|2|no |yes|yes|no |  54.5  |  77.5  |[here](experiment/mnes/2ab8a4ce2af28d2b4b0ff1489fbf392c/details)|
|18|2|yes|yes|yes|no |  52.1  |  75.4  |[here](experiment/mnes/fee86846c6655e2bfb987ff3faf68f67/details)|
|34|1|no |yes|yes|no |  59.5  |  81.5  |[here](experiment/mnes/04d66def32e724c975af3da165d809da/details)|
|34|1|no |no |yes|no |  58.1  |  80.6  |[here](experiment/mnes/5ee11688bb37f52ed64c36a36daa7173/details)|

Extended trainings of above models:

|Layers|Version|Scaled?|FP SC|Pool SC|Approx Sign|Best Top1 Acc|Best Top5 Acc|Details|
|-|-|-|-|-|-|-|-|-|
|18|1|no |yes|yes|no |56.9|79.7|[here](experiment/mnes/c9dfa9473dfc812027736c7c9a54be84/details)|
|34|1|no |yes|yes|no |60.0|82.0|[here](experiment/mnes/cc511769305c05a6abba49707ffbd059/details)|
