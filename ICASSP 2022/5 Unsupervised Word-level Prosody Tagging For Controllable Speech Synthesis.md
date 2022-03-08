# Unsupervised Word-level Prosody Tagging For Controllable Speech Synthesis

[arxiv](https://arxiv.org/pdf/2202.07200.pdf) | code | [sample](https://cantabile-kwok.github.io/word-level-prosody-tagging-control/)

<p align=center>
    <img alt="图 1" src="../img/5%20Unsupervised%20Word-level%20Prosody%20Tagging%20For%20Controllable%20Speech%20Synthesis/IMG_20220308-135712767.png", width="80%">
</p>

## Model

<p align=center>
    <img alt="图 2" src="../img/5%20Unsupervised%20Word-level%20Prosody%20Tagging%20For%20Controllable%20Speech%20Synthesis/IMG_20220308-135755611.png", width="80%">
</p>
从文本入手，提取word-lebel的prosody信息并划分为多个tag

### Prosody tagging

将word-level prosody embedding以phonetic information为判断依据经过决策树进行划分为多个（10）叶子，然后根据prosody information对叶子进行GMM聚类，GMM被设置为5个component，共有$5\times 10=50$种tag
$$t=\arg\underset{k}{\max}\left\{\mathrm{log}\mathcal{N}\left( e|\mu _{k}^{( i)} ,\sum\nolimits_{k}^{( i)}\right) +\mathrm{log} \omega _{k}^{( i)}\right\}$$

## Training and inference

<p align=center>
    <img alt="图 4" src="../img/5%20Unsupervised%20Word-level%20Prosody%20Tagging%20For%20Controllable%20Speech%20Synthesis/IMG_20220308-144918614.png", width="80%">
</p>

## Experiment

### Dataset

1. Single Speaker: **LJSpeech**

### Metrics

1. MUSHRA test
2. Prosody controllability 展示同一单词在多种prosody tag下的mel图
3. MCD
