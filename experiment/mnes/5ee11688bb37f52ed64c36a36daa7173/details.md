```
    --data-path "${mnes_exp_data_path}" \
    --plot-network "meta/plot" \
    --batch-size 64 \
    --dataset imagenet \
    --epochs 60 \
    --gpus 0,1,2,3 \
    --lr 0.001 \
    --lr-factor 0.1 \
    --lr-steps 40,50 \
    --model resnet34_e1 \
    --pool-downsample-sc \
    --wd 0 \
```
![acc.png](acc.png)
[post_process.csv](post_process.csv)
[plot.gv.pdf](plot.gv.pdf)
