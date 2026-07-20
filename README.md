<picture align="center">
  <source media="(prefers-color-scheme: dark)" srcset="docs/icons/cornucopia_lightorange.svg">
  <source media="(prefers-color-scheme: light)"  srcset="docs/icons/cornucopia_orange.svg">
  <img alt="Cornucopia logo" src="https://github.com/balbasty/cornucopia/raw/main/docs/icons/cornucopia_orange.svg">
</picture>

The `cornucopia` package provides a generic framework for preprocessing,
augmentation, and domain randomization; along with an abundance of specific layers,
mostly targeted at (medical) imaging. `cornucopia` is written using a PyTorch
backend, and therefore runs **on the CPU or GPU**.

Cornucopia is *intended* to be used on the GPU for on-line augmentation.
A quick [benchmark](docs/examples/benchmark.ipynb) of affine and elastic augmentation
shows that while cornucopia is slower than [TorchIO](https://github.com/fepegar/torchio)
on the CPU (~ 3s vs 1s), it is greatly accelerated on the GPU (~ 50ms). Note that 
a cornucopia adapter will be available in 
[TorchIO v2](https://docs.torchio.org/2.0/reference/transforms/cornucopia_adapter/?h=corn), 
allowing seamless intergration of cornucopia transformations with TorchIO pipelines.



Since version 0.4, all layers are differentiable, allowing augmentation
parameters to be optimized via backpropagation. 
The **Learn2Synth** framework examplifies this application:

- 📄 [Paper](https://openaccess.thecvf.com/content/ICCV2025/papers/Hu_Learn2Synth_Learning_Optimal_Data_Synthesis_Using_Hypergradients_for_Brain_Image_ICCV_2025_paper.pdf)
- 💻 [Code](https://github.com/HuXiaoling/Learn2Synth)
- 📖 Bibtex
  ```bibtex
  @inproceedings{hu2025learn2synth,
    title={Learn2Synth: Learning Optimal Data Synthesis Using Hypergradients for Brain Image Segmentation},
    author={Hu, Xiaoling and Zeng, Xiangrui and Puonti, Oula and Iglesias, Juan Eugenio and Fischl, Bruce and Balbastre, Ya{\"e}l},
    booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
    pages={20368--20378},
    year={2025}
  }
  ```

## Installation

### Dependencies

- `pytorch >= 1.8`
- `numpy`
- `nibabel`
- `torch-interpol`
- `torch-distmap`

### Pip (release)

```sh
pip install cornucopia
```

### Pip (dev)

```sh
pip install cornucopia@git+https://github.com/balbasty/cornucopia
```

## Documentation

Read the [documentation](https://balbasty.github.io/cornucopia) and in particular:
- [installation](https://balbasty.github.io/cornucopia/install/)
- [get started](https://balbasty.github.io/cornucopia/start/)
- [examples](https://balbasty.github.io/cornucopia/examples/)
- [API](https://balbasty.github.io/cornucopia/api/)

## Other augmentation packages

There are other great, and much more mature, augmentation packages
out-there (although few run on the GPU). Here's a non-exhaustive list:
- [MONAI](https://github.com/Project-MONAI/MONAI)
- [TorchIO](https://github.com/fepegar/torchio)
- [Albumentations](https://github.com/albumentations-team/albumentations) (2D only)
- [Volumentations](https://github.com/ZFTurbo/volumentations) (3D extension of Albumentations)

## Contributions

If you find this project useful and wish to contribute, please reach out!
