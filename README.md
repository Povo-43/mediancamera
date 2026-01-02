# 人が消えるカメラシリーズ

[![GitHub stars](https://img.shields.io/github/stars/Povo-43/mediancamera?style=flat-square)](https://github.com/Povo-43/mediancamera/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Povo-43/mediancamera?style=flat-square)](https://github.com/Povo-43/mediancamera/network/members)

統計的処理により動く人々をリアルタイムまたはバッチ処理で除去し、クリーンな背景画像を生成するWebカメラアプリケーション。4つの異なるアルゴリズムを実装し、用途に応じて最適なモードを選択できます。

## 各モードの比較表
| モード | ファイル名 | アルゴリズム | 処理方式 | 主な用途 |
|--------|------------|-------------|----------|----------|
| Basic | `median.html` | 統計的中央値 | バッチ処理 | 簡単なテスト |
| Live | `live.html` | 指数移動平均 | リアルタイム | ライブデモ |
| Advanced | `live_final.html` | ヒストグラム多数決 | リアルタイム | 高精度処理 |
| Pro | `final.html` | 中央値+距離最適化 | バッチ+Worker | 最高品質出力 | [1](#0-0) 

## 使い分け方

   - 手軽に試す → median.html
   - リアルタイムで見る → live.html  
   - 高精度を求める → live_final.html
   - 最高品質 → final.html

## 技術詳細

### メモリ要件（1080p時）
- median.html: 約41MB（5フレーム）
- live.html: 約16MB（2バッファ）
- live_final.html: 約800MB（ヒストグラム）
- final.html: 約124MB（15フレーム）

### アルゴリズム複雑度
- median.html: O(N log N)
- live.html: O(1)
- live_final.html: O(B) B=128
- final.html: O(N²)

## 動作環境
- Chrome/Edge: 推奨
- Firefox: 一部機能制限あり
- Safari: Web Worker非対応
- モバイル: カメラ切り替え対応

## 公開場所
