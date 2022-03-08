# Paper title

[arxiv](https://arxiv.org/pdf/2110.04451.pdf) | code | [sample](https://gongchenghhu.github.io/ICASSP2022_demo/)

<p align=center>
    <img alt="图 9" src="../img/11%20Using%20Multiple%20Reference%20Audios%20And%20Style%20Embedding%20Constraints%20For%20Speech%20Synthesis/IMG_20220308-155534029.png", width='80%'>
</p>

## Model

<p align=center>
    <img alt="图 10" src="../img/11%20Using%20Multiple%20Reference%20Audios%20And%20Style%20Embedding%20Constraints%20For%20Speech%20Synthesis/IMG_20220308-155639769.png", width='50%'>
</p>

### (a)

用BERT得到sentence embedding将语义相近的speech聚类，作为Reference audios，

### (b)

和普通的Attention不同，这里的的Q'为可训练的vector，S为style Embedding为Reference audios得到的Style embedding，E为最终得到的Style embedding
$$Q=Q^{'} W_{q} ,\ K=SW_{k} ,\ V=SW_{v}$$
$$E=A( Q,K,V) =\mathrm{softmax}\left(\frac{f( Q) f( K)^{T}}{\sqrt{d_{m}}}\right) f( V)$$

## Training and inference

训练时，用TPCE-GST作为Pre-train Style Encoder得到“Target” embedding，可以算loss
$$\mathcal{L}_{total} =\mathcal{L}_{mel} +\mathcal{L}_{s}$$
$$\mathcal{L}_{s} =\mathrm{MSE}\left( E,E^{'}\right) -\mathrm{MI}\left( E,E^{'}\right)$$
其中MI为互信息mutual information

## Experiment

这篇paper消融实验做的特别的足

### Dataset

from the 2013 Blizzard Challenge

### Metrics

1. MOS
2. WER
3. ABX test
