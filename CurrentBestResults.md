## Data preparation

ImageNet data needs to be prepared before training, as described [here](https://gluon-cv.mxnet.io/build/examples_datasets/imagenet.html).

## ResNet

|Layers|Version|Scaled?|Model Size|FP SC|Pool SC|Approx Sign|Flops|Best Top1 Acc|Best Top5 Acc|Epoch|Initial Layers|Opt.|Mode|Warmup|Clip|Details|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|18|e1|no|4.0 MB|yes|yes|no|1.63E+08|60.0|81.9|119|imagenet|radam|cosine|0|1.3|[here](experiment/mnes/4d2fef4e4be333444edc7ebee34bfb73/details.md)|
|18|e1|no|3.98 MB|yes|yes|no|1.14E+08|60.6|82.4|120|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/e0622351034683890e787a1ef9682299/details.md)|
|34|e1|no|5.23 MB|yes|yes|no|1.92E+08|63.2|84.7|120|imagenet|radam|cosine|0|1.3|[here](experiment/mnes/46d848f558af6d1c885bae189420b67c/details.md)|
|34|e1|no|5.21 MB|yes|yes|no|1.43E+08|63.7|84.9|120|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/f2167d224cddbae8d6e0cd002061e5bd/details.md)|

## DenseNet

|Type|Growth-Rate|Init-Features|Reduction|Model Size|Flops|Best Top1 Acc|Best Top5 Acc|Epoch|Initial Layers|Opt.|Mode|Warmup|Clip|Details|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|DenseNet28 (6,6,6,5)|64|64|2.7,2.7,2.2|4.04 MB|2.58E+08|61.7|83.3|120|imagenet|radam|cosine|0|1.3|[here](experiment/mnes/c04facb13305fcbbb2bc9a65a59dd190/details.md)|
|DenseNet28 (6,6,6,5)|64|64|2.7,2.7,2.2|4.03 MB|2.09E+08|62.6|84.0|118|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/3eb4f58286d97e57802107920d90a697/details.md)|
|Densenet37 (6,8,12,6)|64|64|3.3,3.3,4|5.13 MB|2.70E+08|63.3|84.4|117|imagenet|radam|cosine|0|1.3|[here](experiment/mnes/71ab0b402671b22cc16f7c0a2c2fe9bd/details.md)|
|Densenet37 (6,8,12,6)|64|64|3.3,3.3,4|5.12 MB|2.20E+08|64.2|85.1|118|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/859d224e9c5c67386a92c3ebdebf86bf/details.md)|

## MeliusNet

|Type|Growth-Rate|Init-Features|Reduction|Model Size|Flops|Best Top1 Acc|Best Top5 Acc|Epoch|Initial Layers|Opt.|Mode|Warmup|Clip|Details|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|MeliusNet22 (4,5,4,4)|64|64|2.2,2.2,2|3.89 MB|2.58E+08|62.9|84.3|116|imagenet|radam|cosine|0|1.3|[here](experiment/mnes/4c53fae2fac5454ecc1c38d2d9078f91/details.md)|
|MeliusNet22 (4,5,4,4)|64|64|2.2,2.2,2|3.88 MB|2.08E+08|63.6|84.7|118|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/3b3ab86be3cba31b658301ed0f3e2226/details.md)|
|MeliusNet29 (4,6,8,6)|64|64|2.7,2.7,2.7|5.08 MB|2.64E+08|64.9|85.7|118|imagenet|radam|cosine|0|1.3|[here](experiment/mnes/631835a1a42a6bee2d53e2357ce235fe/details.md)|
|MeliusNet29 (4,6,8,6)|64|64|2.7,2.7,2.7|5.07 MB|2.14E+08|65.8|86.2|118|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/b75427ab9a420b4bd5cbc1472e05b558/details.md)|
|MeliusNet42 (5,8,14,10)|64|64|2.2,2.7,2.7|10.1 MB|3.25E+08|69.2|88.3|119|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/27dec8d4da3dec75b65653643cc02eca/details.md)|
|MeliusNet59 (6,12,24,12)|64|64|2.5,3,3.5|17.39 MB|5.32E+08|70.7|89.2|130|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/b32820e3e829cd0d9715848cc2d8ba07/details.md)|
|MeliusNetA (4,5,5,6)|64|64|2,2,2|4.05 MB|1.63E+08|63.4|84.2|117|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/b20876e68c314e4908b5067df11a9333/details.md)|
|MeliusNetB (4,6,8,6)|64|64|2.2,2.4,2.4|5.0 MB|1.96E+08|65.7|85.9|119|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/ac6b05b34203a249cb9568ea60d84be9/details.md)|
|MeliusNetC (3,5,10,6)|64|64|2,2.4,3|4.46 MB|1.50E+08|64.1|85.0|120|grouped_stem|radam|cosine|0|1.3|[here](experiment/mnes/c02c02a12a5e18be506533bfd730bcb8/details.md)|
