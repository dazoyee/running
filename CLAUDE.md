# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

マラソン大会に向けた練習計画・結果管理用のリポジトリ。ソースコードは存在せず、Markdown/CSVによるデータ管理のみ。ビルド・lint・テストの概念やコマンドは存在しない。

## ディレクトリ構成

- `templates/`: 雛形一式（`plan.md` / `results.csv` / `splits.csv` / `evaluations.md`）
- `races/<年月日-大会名>/`: 大会ごとの実運用ファイル。大会名・開催日が決まった時点で `templates/` の内容をコピーして作成する。練習データは大会ごとに完全分離し、大会をまたぐ通しログは持たない

## 各ファイルの役割とデータ規約

- `plan.md`: ベース期／ビルド期／ピーク期／テーパー期の期分けと週次メニュー
- `results.csv`: 1走行1行のサマリー（`date, start_time, end_time, distance_km, avg_pace_sec, best_pace_sec, running_time_sec, elapsed_time_sec, calories_kcal, avg_cadence_spm, elevation_gain_m, elevation_loss_m, avg_hr_bpm, max_hr_bpm`）。時間・ペースは秒数など機械可読な数値のみで保存し、`6'23"` のような表示用フォーマット文字列は持たない
- `splits.csv`: km単位のスプリット（`date, km, split_pace_sec, pace_diff_sec, elevation_change_m, hr_bpm`）。`date` で `results.csv` の行と紐付ける
- `evaluations.md`: 日付ごとに追記する練習評価ログ。各エントリは「計画照合」「目標に対する進捗」「体調・回復度・怪我リスク」「次回メニュー提案」の4観点で記述する

## 運用ワークフロー

Nike Run Club等の練習記録のスクリーンショットや文字起こしを渡された場合、値を抽出して該当大会ディレクトリの `results.csv` / `splits.csv` に追記し、その場で `evaluations.md` に評価コメントを追記するところまでを一気通貫で行う。
