```
    --data-path "${mnes_exp_data_path}" \
    --plot-network "meta/plot" \
    --add-relu-to-downsample \
    --batch-size 128 \
    --dataset imagenet \
    --epochs 50 \
    --fp-downsample-sc \
    --gpus 0,1,2,3 \
    --growth-rate 160 \
    --init-features 128 \
    --lr 0.001 \
    --lr-factor 0.1 \
    --lr-steps 40,45 \
    --model densenet21 \
    --reduction 2,2,2 \
    --wd 0 \
```
![acc.png](acc.png)
[post_process.csv](post_process.csv)
[plot.gv.pdf](plot.gv.pdf)
