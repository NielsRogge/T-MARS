# T-MARS
Official repository for the paper [T-MARS: Improving Visual Representations by Circumventing Text Feature Learning](https://arxiv.org/abs/2307.03132).  
Webpage: https://tmars-clip.github.io/

## T-MARS Text Masking Code
We use FAST (https://github.com/czczup/FAST) as the base algorithm for text detection and MMOCR (https://mmocr.readthedocs.io/en/dev-1.x/) for text recognition i.e. reading the text. This repository shares the combined implementation of FAST and MMOCR for running on web-scales (adapted from DataComp https://www.datacomp.ai/).


## Installation

```sh
pip install git+https://github.com/mlfoundations/dataset2metadata
```

Refer to MMOCR installation instructions [here](https://mmocr.readthedocs.io/en/dev-1.x/get_started/install.html).

## Text detection and recognition
Please refer to [text_snake_wrapper.py](https://github.com/locuslab/T-MARS/blob/main/dataset2metadata/text_detection/text_snake_wrapper.py) for the main implementation of text detection (FAST) and text recognition (MMOCR). 
Download the text detection model : 
```
wget https://github.com/czczup/FAST/releases/download/release/fast_tiny_tt_512_finetune_ic17mlt.pth
```

## RUN
Please see the [examples/](https://github.com/locuslab/T-MARS/tree/main/examples/slurm) folder for ways in which dataset2metadata is to be used for running T-MARS on webscale. You can specify the tar file paths in [text_template.yml](https://github.com/locuslab/T-MARS/blob/main/examples/slurm/text_template.yml) and create multiple such template files using [prepare_jobs.py](https://github.com/locuslab/T-MARS/blob/main/examples/slurm/prepare_jobs.py)

```
dataset2metadata --yml examples/text_template.yml
```

## Acknowlegements
We thank the authors of FAST, MMOCR and DataComp team for open sourcing their code bases. 
