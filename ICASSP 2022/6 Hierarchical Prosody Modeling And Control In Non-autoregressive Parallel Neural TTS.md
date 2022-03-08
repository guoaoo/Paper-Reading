# Paper title

[arxiv](https://arxiv.org/pdf/2110.02952.pdf) | code | [sample](https://apple.github.io/parallel-tts-hierarchical-prosody-control/)

<p align=center>
    <img alt="图 5" src="../img/6%20Hierarchical%20Prosody%20Modeling%20And%20Control%20In%20Non-autoregressive%20Parallel%20Neural%20TTS/IMG_20220308-151326000.png", width="80%">
</p>

## Model

<p align=center>
    <img alt="图 6" src="../img/6%20Hierarchical%20Prosody%20Modeling%20And%20Control%20In%20Non-autoregressive%20Parallel%20Neural%20TTS/IMG_20220308-151420523.png", width="60%">
</p>

<p align=center>
    <img alt="图 7" src="../img/6%20Hierarchical%20Prosody%20Modeling%20And%20Control%20In%20Non-autoregressive%20Parallel%20Neural%20TTS/IMG_20220308-151433920.png", width="60%">
</p>

### Modules

用pitch, phone duration, speech energy, and spectral tilt来表示prosody，直接在原始模型上加上这个信息的predictor

## Training and inference

## Experiment

### Dataset

Internal dataset, a man and a woman
> We use data from two American English speakers, a high-pitched speaker with 36-hour dataset (Voice 1), and a low-pitched speaker with 23-hour dataset (Voice 2).

### Metrics

1. MOS
2. AB preference test
