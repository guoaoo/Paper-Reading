# Improving Emotional Speech Synthesis By Using Sus-constrained Vae And Text Encoder Aggregation

[arxiv]([https](https://arxiv.org/pdf/2110.09780.pdf)) | code | [sample](https://fyyang1996.github.io/emotion/)

<p align=center>
    <img alt="图 8" src="../img/3%20IMPROVING%20EMOTIONAL%20SPEECH%20SYNTHESIS%20BY%20USING%20SUS-CONSTRAINED%20VAE%20AND%20TEXT%20ENCODER%20AGGREGATION/IMG_20220307-220545946.png", width="80%">
</p>

## Model

<p align=center>
    <img alt="图 7" src="../img/3%20IMPROVING%20EMOTIONAL%20SPEECH%20SYNTHESIS%20BY%20USING%20SUS-CONSTRAINED%20VAE%20AND%20TEXT%20ENCODER%20AGGREGATION/IMG_20220307-220431679.png", width="80%">
</p>

用VAE来更好的得到Emotion embedding，花样玩embedding和attention

### Modules

#### SUS-constrained VAE

本文认为，VAE的均值之间的距离应该和标准差类似，均值之间的距离如果比标准差大很多的话，隐变量会更倾向于均值，如果均值之间的距离很小，隐变量会倾向于与输入独立，因此提出了Surface of the Unit Sphere (SUS) constrained VAE，使标准差在所有维度上都趋向于一个适合的常数
$$loss_{SUS} =\left(\sqrt{\sum \left( \mu ^{2}\right)} -1\right)^{2}$$
$$\sigma =constant$$

#### Combined multi-query

用VAE来算一个Multi-Query的的权重
$$Q^{a} =\mathrm{DNN}( vae)$$
$$Q^{c} =Q^{t} +\mathrm{Sigmiod}( w) Q^{a}$$

## Experiment

中文prosody
phones, tones, character segments
prosodic word (PW), phonological phrase (PPH) and intonation phrase (IPH)

### Dataset

Internal Mandarin dataset

### Metrics

1. MCD
2. A/B preference test
