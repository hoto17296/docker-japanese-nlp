# Docker Japanese NLP
一瞬で(日本語)自然言語処理の分析環境を用意するための Docker イメージ

## パッケージ
- Python 3 (Anaconda 3)
- gensim
- MeCab
  - mecab-python3
  - mecab-ipadic-neologd
  - neologdn
- CRF++
- CaboCha
- fastText
- spaCy
- janome
- pykakasi

## Jupyter Notebook
Docker Volume に Notebook を保存することで、コンテナを削除した際に Notebook が消えてしまわないようにする

### Notebook を保存する Volume を作成
``` console
$ docker volume create notebooks
```

### Jupyter を起動
``` console
$ docker run --rm -it -p 8888:8888 -v notebooks:/notebooks hoto17296/japanese-nlp \
    jupyter notebook --notebook-dir=/notebooks
```
