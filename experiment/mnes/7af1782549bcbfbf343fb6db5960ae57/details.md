```
    --plot-network "meta/plot" \
    --batch-size 128 \
    --dataset imagenet \
    --epochs 40 \
    --gpus 0,1 \
    --lr 0.001 \
    --lr-factor 0.1 \
    --lr-steps 34,37 \
    --model resnet18_v2-scaled \
    --wd 0 \
```
![acc.png](acc.png)
[post_process.csv](post_process.csv)
[plot.gv.pdf](plot.gv.pdf)
