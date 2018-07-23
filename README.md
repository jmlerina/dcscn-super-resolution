## Direto ao ponto

Maiores informações estão no projeto original.

**Evaluate**: Learned weights for some parameters are included in this GitHub. Execute **evaluate.py** with these args below and you get results in **output** directory. When you want to evaluate with other parameters, try training first then evaluate with same parameters as training have done. Results will be logged at log.txt, please check.

Some pre-trained models are included.

```
# evaluating set14 dataset
python evaluate.py --test_dataset=set14 --save_results=true

# evaluating set5 dataset with small model
python evaluate.py --test_dataset=set5 --save_results=true --layers=8 --filters=96

# evaluating all(set5,set14,bsd100) dataset
python evaluate.py --test_dataset=all

# evaluate our compact version of DCSCN (c-DCSCN)
python evaluate.py --scale=2 --layers=7 --filters=32 --min_filters=8 --filters_decay_gamma=1.2 --nin_filters=24 --nin_filters2=8 --reconstruct_layers=0 --self_ensemble=1 --batch_image_size=32 --pixel_shuffler_filters=1 --test_dataset=all
```

**Apply to your own image**: Place your image file in this project directory. And then run "sr.py --file 'your_image_file'" to apply Super Resolution. Results will be generated in **output** directory. Please note you should use same args which you used for training.

If you want to apply this model on your image001.png file, try those.

```
# apply super resolution on image001.jpg (then see results at output directory)
python sr.py --file=your_file.png

# apply super resolution with small model
python sr.py --file=your_file.png --layers=8 --filters=96
```
