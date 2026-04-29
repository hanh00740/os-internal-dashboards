# OS Internal Dashboards

オーガニックサイエンス内部分析ダッシュボード集約リポジトリ。

## 🌐 公開URL (Cloud Storage hosted)

**Production**: https://storage.googleapis.com/os-internal-dashboards/index.html

## Available Dashboards

- **ECAI 購入後ナーチャリング As-IS** - LINE/ECAIの購入後ステップメッセージ現状分析

## Architecture

```
Source (Git)              →  Hosting (GCP)
  ↓                            ↓
github.com/...            →  gs://os-internal-dashboards/ (dashboard-459108)
  ↓                            ↓
git push                  →  python3 gcs_deploy_dashboards.py
                              ↓
                              https://storage.googleapis.com/os-internal-dashboards/
                              ↓
                              Notion embeds
```

## How to Update

```bash
cd /home/hanh00740/projects/dashboards/os-internal-dashboards
# 1. Edit index.html or other files
# 2. Commit to Git (source of truth)
git add -A && git commit -m "update: <description>" && git push

# 3. Deploy to Cloud Storage
cd /home/hanh00740/projects && python3 gcs_deploy_dashboards.py
```

The dashboard updates within 5 minutes (Cache-Control: max-age=300).

## GCP Configuration

- **Project**: dashboard-459108
- **Bucket**: gs://os-internal-dashboards
- **Region**: asia-northeast1
- **Public access**: allUsers / Storage Object Viewer
- **Service Account**: os-273@possible-maxim-461108-j6.iam.gserviceaccount.com (with Storage Admin on dashboard-459108)
- **Console**: https://console.cloud.google.com/storage/browser/os-internal-dashboards?project=dashboard-459108

## Source Data

ECAI抽出データ: `/tmp/ecai_*.json` (Linux server)
分析スクリプト: `/home/hanh00740/projects/ecai_step_*.py`
