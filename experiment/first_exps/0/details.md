```
    --batch-size 128 \
    --dataset imagenet \
    --epochs 50 \
    --gpus 0,1 \
    --lr 0.001 \
    --lr-factor 0.1 \
    --lr-steps 40,45 \
    --model resnet18_v1
```
![acc](acc.png)
[post_process.csv](post_process.csv)
[plot.gv.pdf](plot.gv.pdf)