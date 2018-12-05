```
    --data-path "${mnes_exp_data_path}" \
    --plot-network "meta/plot" \
    --batch-size 128 \
    --dataset cifar10 \
    --epochs 150 \
    --gpus 0 \
    --growth-rate 128 \
    --init-features 128 \
    --lr 0.01 \
    --lr-factor 0.3 \
    --lr-steps 75,100,125 \
    --model densenet21 \
    --reduction 1,1.4,1.4 \
    --wd 0 \
```
![acc.png](acc.png)
[post_process.csv](post_process.csv)
[plot.gv.pdf](plot.gv.pdf)
