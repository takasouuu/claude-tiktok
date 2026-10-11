# claude-tiktok

TikTok写真投稿用の公開ページと写真置き場（GitHub Pages: https://takasouuu.github.io/claude-tiktok/ ）。
投稿スクリプト本体は claude-sns リポジトリの `tools/tiktok/` にある。

| パス | 用途 |
|---|---|
| `index.html` | アプリのトップページ（TikTok DevelopersのWebsite URL） |
| `terms.html` / `privacy.html` | 利用規約・プライバシーポリシー（TikTok Developersに登録するURL） |
| `callback.html` | Login KitのRedirect URI。認可後にこのページのURLを `auth` に貼り付ける |
| `photos/` | 投稿する写真（JPG/WEBP）。TikTokがここのURLから画像を取得する |

- このリポジトリは公開。`photos/` に置いた写真は、TikTok上で非公開のうちから誰でも見られる。
  **位置情報（EXIF）を消してから**pushし、投稿が済んだ写真は消してよい。
- クライアントキー・シークレット・トークンは絶対にここへコミットしない。
- TikTokのURL所有者確認用ファイルは、指示されたファイル名のままリポジトリ直下に置く。

## kabu/（株用アカウント）

株用TikTokアカウントの投稿写真は `kabu/<日付>/<セット>/NN.jpg` に置く（`photos/` とは分ける）。
claude-trade-analysis の `scripts/tiktok_inbox.py` が毎日自動で push し、下書き（受信箱）として送る。
