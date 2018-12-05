```
    --batch-size 128 \
    --dataset imagenet \
    --epochs 50 \
    --gpus 2,3 \
    --bits 1 \
    --bits-a 1 \
    --lr 0.001 \
    --lr-factor 0.1 \
    --lr-steps 40,45 \
    --model resnet18_v1-scaled
    --wd 0.0
```
![acc](acc.png)
[plot.gv.pdf](plot.gv.pdf)
[post_process.csv](post_process.csv)