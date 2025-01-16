## (AAAI2025) StructSR: Refuse Spurious Details in Real-World Image Super-Resolution

[Project Page]: https://lycexe.github.io/StructSR-project/
[Arxiv Page]: https://arxiv.org/abs/2501.05777

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

### License

This project is licensed under [MIT License](https://github.com/LYCEXE/StructSR/blob/main/LICENSE). Redistribution and use should follow this license.

### Acknowledgement

This project is based on [stablediffusion](https://github.com/Stability-AI/stablediffusion), [latent-diffusion](https://github.com/CompVis/latent-diffusion), [SPADE](https://github.com/NVlabs/SPADE), [mixture-of-diffusers](https://github.com/albarji/mixture-of-diffusers), [BasicSR](https://github.com/XPixelGroup/BasicSR) and [StructSR](https://github.com/IceClear/StableSR). Thanks for their awesome work.

### Contact

If you have any questions, please feel free to reach me out at `li509383050@gmail.com`.

### BibTeX

```
@article{li2025structsr,
  title={StructSR: Refuse Spurious Details in Real-World Image Super-Resolution},
  author={Li, Yachao and Liang, Dong and Ding, Tianyu and Huang, Sheng-Jun},
  journal={arXiv preprint arXiv:2501.05777},
  year={2025}
}
```

