```
python image_classification.py \
    --data-dir ~/.mxnet/datasets/imagenet/ \
    --augmentation medium \
    --batch-size 32 \
    --clip-threshold 1.3 \
    --dataset imagenet \
    --downsample-structure bn,max_pool,relu,cs:16,fp_conv:2 \
    --epochs 120 \
    --gpus 0,1 \
    --initial-layers grouped_stem \
    --lr 0.002 \
    --lr-mode cosine \
    --mode hybrid \
    --model meliusnet29_2 \
    --optimizer radam \
```
![acc.png](acc.png)

## Files

- [post_process.csv](post_process.csv)
- [plot.gv.pdf](plot.gv.pdf)

