
## StructSR: Refuse Spurious Details in Real-World Image Super-Resolution

### Dependencies and Installation
- Pytorch == 1.12.1
- CUDA == 11.7
- pytorch-lightning==1.4.2
- xformers == 0.0.16 (Optional)
- Other required packages in `environment.yaml`
```
# Create a conda environment and activate it
conda env create --file environment.yaml
conda activate structsr

# Install xformers
conda install xformers -c xformers/label/dev

# Install taming & clip
pip install -e git+https://github.com/CompVis/taming-transformers.git@master#egg=taming-transformers
pip install -e git+https://github.com/openai/CLIP.git@main#egg=clip
pip install -e .
```

#### Test 

Download the baseline  models from [[Google Driver](https://drive.google.com/drive/folders/1EC9b1RIlZCRi4WjxlzUmHQ_3ZxI-N4x0?usp=sharing)].

```
python scripts/StructSR.py --config configs/stableSRNew/v2-finetune_text_T_512.yaml --ckpt CKPT_PATH --vqgan_ckpt VQGANCKPT_PATH --init-img INPUT_PATH --outdir OUT_DIR --ddpm_steps 200 --dec_w 0.5 --colorfix_type adain --lamda 0.3
```

``` --lamda
lamda: Used for control the timesteps of $T_{SAS}$
```



