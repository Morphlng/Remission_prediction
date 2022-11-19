# Remission_prediction

Code for CCF competition ["Criminal remission time prediction"](https://www.datafountain.cn/competitions/611/ranking?isRedance=0&amp;sch=2034)

## Dataset

1. 百度网盘：https://pan.baidu.com/s/1rWO4gc8SgFwHC1DhmlGgkA?pwd=ylys
提取码：ylys 

2. 赛事官网：https://www.datafountain.cn/competitions/611

> Download to root folder and rename into "data"

## Setup

> Assume conda environment is already installed. If not, please refer to [Miniconda setup](https://docs.conda.io/en/latest/miniconda.html)

1. Create a new conda env: `conda create -n torch python=3.8`. After setup, activate through `conda activate torch`
2. Install Pytorch following [official tutorial](https://pytorch.org/get-started/locally/)
3. Install dependencies: `pip install numpy pandas scikit-learn transformers`
4. Run the jupyter notebook

## Best Model

Currently, best result comes with following arguments：

1. Bert Model: `hfl/chinese-roberta-wwm-ext-large`
2. Input max_length: 512 (truncate and paddle enabled)
3. Batch_size: 8
4. Learning_rate: 2e-5
5. Weight_decay: 0.01
6. Training_epoch: 50
7. Metric: $FinalScore = \sum_{i=1}^{N}Score_{i} \times 0.7 + ExtAcc \times 0.3$
8. **Clip First Sentence**

**TODO**: Bert is not able to accept text longer than 510 words, clipping out the first sentence is not enough. 