+++
title = "Distributed System of Apocalypse"
date = 2019-07-23

[taxonomies]
categories = ["distributed system", "研究", "進捗"]
tags = ["distributed system"]

+++

分散システムについて調べたことをまとめていきます。
- FAST'19の論文調査(https://www.usenix.org/sites/default/files/fast19_full-proceedings.pdf)

<!-- more -->

FASTはFile and Storage Technologiesの略で、USENIX(Unix Useer Group)が主催するカンファレンスの一つです。
以下、分野ごとに、FAST'19でAcceptされた論文をまとめていきます。

## Persistent Memory Systems
- Reaping the performance of fast NVM storage with uDepot
  - めっちゃ速いNVMの技術を活かしきれてないので、活かすための提案をする
- Optimizing Systems for Byte-Addressable NVM by Reducing Bit Flipping
  - 書き込みを少なくするよりもビットフリップが少ない方がいい
  - PCM, BNVM
  - ビットフリップを減らす研究らしい
- Write-Optimized Dynamic Hashing for Persistent Memor
  - レイテンシが低いbyte-addressable persistent memory(PM)などは最適化のためにデータ構造を考え直さなければいけない
  - 一定のハッシュテーブルの検索時間を保ちながら、動的メモリブロック管理のオーバヘッドを減らすための手法を提案する
- Software Wear Management for Persistent Memories
  - 商用利用が間近に迫ったPMの耐久をあげるためにOSベースのwear-managementを提案

## File Systems
- Storage Gardening: Using a Virtualization Layer forEfficient Defragmentation in the WAFL File System
  - WAFL(Write Anywhere File Layout)の効率的なデフラグのための仮想化レイヤーの説明をするらしい
- Pay Migration Tax to Homeland:Anchor-based Scalable Reference Counting for Multicores
  - FileSystemはマルチコアの対応が十分じゃない
  - 参照カウントが性能低下の原因となっている
  - いい参照カウントを提案している
- Speculative Encryption on GPU Applied to Cryptographic File Systems
  - Cryptographic File Systems(CFS)
  - CTRモードとは
  - 暗号化ファイルシステムのためのGPUを使うやつらしい

## Deduplication
- Sketching Volume Capacities in Deduplicated Storage
  - 重複ストレージ環境での容量の分析手法の提案
  - スケッチベースの予測
- Finesse: Fine-Grained Feature Locality based Fast Resemblance Detectionfor Post-Deduplication Delta Compression
  - delta compression
  - N-transform Super-Feature
  - delta compressionのための類似性を検索する速い手法を提供
- Sliding Look-Back Window Assisted Data Chunk Rewriting for ImprovingDeduplication Restore Performance
  - データの再格納を速くするためにフラグメンテーションを減らすのと、コンテナベースの重複排除システムの読み取り拡大に焦点を合わせた提案手法

## Storage Potpourri
- DistCache: Provable Load Balancing for Large-Scale Storage Systemswith Distributed Caching
  - Distributedキャッシュの新しい手法の提案！！！探してたやつかも
- GearDB: A GC-free Key-Value Store on HM-SMR Drives with Gear Compaction
  - Host-managed  shingled  magnetic  recording  drives  (HM-SMR)
  - HM-SMRに最適化されたGCがないKVストアなDBの提案
- SPEICHER: Securing LSM-based Key-Value Stores using Shielded Execution
  - KVデータベースの提案、LSMベース

## NVB File and Storage Systems
- SLM-DB: Single-Level Key-Value Store with Persistent Memory
  - Key-value storeのパフォーマンスを高めるためにどうしたらPMを活用できるか
- Ziggurat: A Tiered File System for Non-Volatile Main Memories and Disks
  - Non-Volatile Main Memory(NVMM)
  - NVMMと遅いディスクを組み合わせたファイルシステムの提案
- Orion: A Distributed File System for Non-Volatile Main Memoriesand RDMA-Capable Networks
  - distributed file system!!! for NVMM
  - ネットワークのこととか考えてる！！！

## Big Systems
- INSTalytics: Cluster Filesystem Co-design for Big-data Analytics
  - ビッグデータのクラスターファイルシステム
- GRAPHONE: A Data Store for Real-time Analytics on Evolving Graphs
  - グラフのデータストア的な
  - 今までのやつはパフォーマンスが悪いから
- Automatic, Application-Aware I/O Forwarding Resource Allocation
  - I/O forwarding architecture
  - 動的フォワーディングリソースアロケーションのための自動で動くやつを提案

## Flash and Emerging Storage Systems
- Design Tradeoffs for SSD Reliability
  - SSDの信頼性について、デザインとのトレードオフを分析
- Fully Automatic Stream Management for Multi-Streamed SSDsUsing Program Contexts
  - Multi-streamed SSD
  - 完全に自動なstream管理のなんかを提案
- Large-Scale Graph Processing on Emerging Storage Devices
  - emerging storage devices
  - 悪いところを指摘して、グラフ処理のなんかを提案する...らしい

## Erasure Coding and Reliability
- Fast Erasure Coding for Data Storage: A Comprehensive Study of theAcceleration Techniques
  - Erasure codingのための手法を、今までの(bitmatrix, optimizing computation schedule, common XOR operation reduction, caching management, vectorization)を組み合わせてやるらしい
- OpenEC: Toward Unified and Configurable Erasure Coding Management inDistributed Storage Systems
  - いろんなerasure codingの解決をするためのフレームワークの提案
- Cluster storage systems gotta have HeART:improving storage efficiency by exploiting disk-reliability heterogeneity
  - 冗長性の設定を変えてなんか作る！！！
- caleCheck: A Single-Machine Approach forDiscovering Scalability Bugs in Large Distributed Systems
  - 拡張性のバグを見つけるやつ

## 感想的な
いやー、収穫ありだな。分散システムのキャッシュ見つけたし。
いやーあはははは！
