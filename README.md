# OS Internal Dashboards

オーガニックサイエンス内部分析ダッシュボード集約リポジトリ。

## Available Dashboards

- **[ECAI 購入後ナーチャリング As-IS](https://hanh00740.github.io/os-internal-dashboards/)** - LINE/ECAIの購入後ステップメッセージ現状分析

## How to Update

```bash
cd /home/hanh00740/projects/dashboards/os-internal-dashboards
# Edit index.html or other files
git add -A
git commit -m "update: <description>"
git push
```

GitHub Pages will auto-deploy in ~1 minute.

## Source Data

ECAI抽出データ: `/tmp/ecai_*.json` (Linux server)
分析スクリプト: `/home/hanh00740/projects/ecai_step_*.py`
