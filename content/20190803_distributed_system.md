+++
title = "キャッシュの論文をさらっと読んでみた"
date = 2019-08-20

[taxonomies]
categories = ["cache", "研究", "進捗"]
tags = ["cache"]

+++

A Fast Analytical Model of Fully Associative Caches

<!-- more -->

# A Fast Analytical Model of Fully Associative Caches
- PLDI2019のAccepted paper

## 一言説明
- 計算時に，ローカルのプロパティを理解するのは簡単だが，グローバルなステートに依存するキャッシュは予測が難しい
- そのため，プログラマーは良くデータ移動のコストを見誤る
- 既存のキャッシュモデルやシミュレータはキャッシュミス情報を提供するが，それは計算的にコストが高い
- Least Recently Used(LRU)方式のlightweight cache modelを提案する
  - シンボリックカウントの手法を使用して，メモリアクセスを列挙せずにキャッシュミスをカウントする
    1. 各メモリアクセスのスタック距離を割り出す
    2. キャッシュサイズよりも大きい距離でメモリアクセスをカウント

## 論文のキモ
- [HayStack](https://github.com/spcl/haystack)
- キャッシュミスのカウントにBarvinok algorithmを用いている
- 高精度，高速
- プログラマーにキャッシュの感覚を提供！

## 既存研究との違い
- スタック距離を計算して，キャッシュ容量より大きいスタック距離のインスタンスをカウントしていく

## 検証内容
- 正確性，パフォーマンスについて調べた後，他の手法と１対１で比較している

## 次に読む論文
キャッシュの振る舞い分析には
- シミュレータ
- プロファイリング
- モデル
の３つがある．
基礎的(古い）論文と発展的（最近）の論文を上げておく

### シミュレータ
- Dinero IV Trace-Driven Uniprocessor Cache Simulator
- On modeling and analyzing cache hierarchies using CASPER
- The gem5 simulator

### プロファイリング
- Evaluation techniques for storage hierarchies
- Locality analysis through static parallel sampling

### モデル
- An analytical cache model
- Analytical modeling of cache behavior for affine programs