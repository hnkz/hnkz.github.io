+++
title = "The ITC Distributed File System Principles and Design"
date = 2019-06-26

[taxonomies]
categories = ["distributed system", "research", "paper research"]
tags = ["distributed system", "filesystem"]

+++

分散システムについて調べていたらこの論文を見つけたので、読んでみました。

```
M. Satyanarayanan, John H. Howard, David A. Nichols, Robert N. Sidebotham, Alfred Z. Spector, Michael J. West, "The ITC Distributed File System Principles and Design", “Proceedings of the Tenth ACM Symposium on Operating Systems Principles, Vol. 19.
```

## 一言説明
- CMUでのワークステーション用の分散ファイルシステムの構築
- スケールアウトしながら長期間使いたいための設計をした
- 多種多様な人が使うからセキュリティについても考慮した
- ファイル全体をキャッシュするのがこのFSのキモらしい
- ファイルシステムの設計からサーバの構成まで、色々と書いてある

<!-- more -->

## まとめ
論文というよりかは、解説？ポエム？よくわからないのでまとめます。

### 1章 イントロ
- 使用環境について
- CMUのキャンパスで学生や教員とかが使うっぽいワークステーション
- そのためのファイルシステムを構築した

### 2章 デザイン
- OSを作るより簡単だから分散ファイルシステムを作ったらしい
- 位置情報を含めない、一意な名前を持つファイル
- Viceが計算リソースの集合体、Viceにアクセスする個人のワークステーションがVirtue

### 3章　詳細なデザイン

#### 名前と位置
- 共有ファイルスペースと、マシン固有のローカルなファイルスペースに別れている

#### レプリケーション
- キャッシュを行う
- ファイルを開いて更新している間はキャッシュサーバにあるファイルに更新が適用され、Virtueは直接Viceと接続しない
- ファイルを閉じたら、適切な管理サーバにファイルが送られる
- リードオンリーのリプリケーションもしている

#### 関数インターフェース
- Vice-Virtueを繋ぐインターフェースとVirtueでファイルを見るためのインターフェースの二つが必要

#### セキュリティ
- 違反な情報のリリース、修正を処理する
- Viceでは暗号化を行なっている
- 認証も行う
  - 接続時、共通鍵をVice, Virtueは保持している
  - 接続後、セッションキーを渡され、その鍵で通信を行う

### 4章 デザイン主義
- 

### 5章 プロトタイプ

### 6章 他のシステムとの関係
- 他の分散ファイルシステムとの比較とかもしてる

### 7章 結論
- 色々まとめ書いてある。読むといい。


## 次に読むべき論文
- Performance of Cache in Distributed Systems
- System for distributed software quality improvement
    - google
- Map-reduce ready distributed file system
- Redundant, fault-tolerant, distributed remote procedure call cache in a storage system
- Implementation of multiple thread pools based ondistribution of service times