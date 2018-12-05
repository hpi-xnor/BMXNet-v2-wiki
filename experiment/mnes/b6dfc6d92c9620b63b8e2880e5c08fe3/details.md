```
    --plot-network "meta/plot" \
    --batch-size 128 \
    --dataset cifar10 \
    --epochs 150 \
    --fp-downsample-sc \
    --gpus 0 \
    --lr 0.01 \
    --lr-factor 0.3 \
    --lr-steps 75,100,125 \
    --model resnet18_e1-scaled \
    --pool-downsample-sc \
    --use-approx-sign \
    --wd 0 \
```
![acc.png](acc.png)
[post_process.csv](post_process.csv)
[plot.gv.pdf](plot.gv.pdf)
