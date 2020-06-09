```
python image_classification.py \
    --data-dir ~/.mxnet/datasets/imagenet/ \
    --augmentation medium \
    --batch-size 16 \
    --clip-threshold 1.3 \
    --dataset imagenet \
    --epochs 120 \
    --gpus 0,1,2,3 \
    --initial-layers grouped_stem \
    --lr 0.002 \
    --lr-mode cosine \
    --mode hybrid \
    --model meliusnet42 \
    --optimizer radam \
```
![acc.png](acc.png)

## Files

- [post_process.csv](post_process.csv)
- [plot.gv.pdf](plot.gv.pdf)

