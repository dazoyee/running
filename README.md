# running

マラソン大会に向けた練習計画・結果管理用のリポジトリ。Markdown/CSVでデータを管理し、ソースコードは持たない。

## セットアップ

前提条件: Git（ローカルリポジトリとして管理）。特別なインストール作業は不要。

## 使い方

大会の開催が決まったら `templates/` の内容を `races/<年月日-大会名>/` にコピーして運用する。

```bash
mkdir -p races/2026-11-08-fukuoka-marathon
cp templates/* races/2026-11-08-fukuoka-marathon/
```

- `plan.md`: 期分け練習計画（週次メニュー）
- `results.csv`: 1走行ごとの記録（Nike Run Club等から抽出した数値を追記）
- `splits.csv`: km単位のスプリット記録
- `evaluations.md`: 練習ごとの評価ログ

データ項目の詳細な規約は `CLAUDE.md` を参照。
