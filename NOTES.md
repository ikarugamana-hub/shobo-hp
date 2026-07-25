# 作業ノート(NOTES.md)

複数のPCで並行して更新作業を行うため、作業内容をこのファイルに記録して共有します。

## 運用ルール

- **作業を始める前に必ず `git pull` を実行**し、このファイルの最新の記録を確認する。
- **作業が終わったら、下記フォーマットで追記して push する。**
- 記載は事実ベースで簡潔に。推測や未確認事項は「未確認」と明記する。
- **公開リポジトリのため、顧客名・契約金額・原価・個人情報は記載しない。**

### 追記フォーマット

```
### YYYY-MM-DD / 作業PC名(任意)
- 変更内容:
- 影響範囲(ファイル・ページ):
- 未対応・引き継ぎ事項:
```

---

## 作業履歴

### 2026-07-25 / Mac(manabutsurumaki)

- **変更内容:** ローカルリポジトリを `origin/main` の最新(`fa1c713`)まで fast-forward で更新(114コミット分の差分を取り込み)。あわせて本ファイル `NOTES.md` を新規作成。
- **影響範囲:** ローカル環境のみ(サイトの表示内容に対する変更なし)。`NOTES.md` の追加のみがリポジトリへの変更。
- **確認したこと:** ローカルサーバー(`python3 -m http.server`)でトップページの表示を確認。ヒーロー動画・ロゴ・「初回お試し無償クリーニング・サンプル相談 実施中」バナー・電話/フォーム固定バーが正常に表示された。
- **削除したファイル:** 未追跡のまま残っていた `消防HP案8_ナビゲーション.html`(旧ファイルの残骸)。pull 時点で既に消えていたため、追加の削除操作は不要だった。
- **未対応・引き継ぎ事項:**
  - 今回取り込んだ 114 コミットの内容(下記「主な更新内容」)は差分から読み取ったものであり、各ページの表示確認はトップページのみ。`kansen.html` / `sp.html` / `story_cleaning.dc.html` / `404.html` は未確認。
  - この履歴は 2026-07-25 以降に上記フォーマットで追記していく運用とする。

#### 取り込んだ主な更新内容(`c419c0c` → `fa1c713` の差分より)

- 新規ページの追加:`kansen.html`、`sp.html`、`404.html`
- 旧ファイルの削除:`support.js`、`HP8_nav.dc.html`、`story_infection.dc.html`、`story_rental.dc.html`、`story_rental_template.txt`、`UNILEASE 感染防止衣 LP (standalone).html`
- SEO 対応:`robots.txt`、`sitemap.xml`、OGP 画像(`og-top.jpg` / `og-kansen.jpg` / `og-cleaning.jpg`)を追加
- パフォーマンス改善:画像の webp 化、`douga0.mp4` を約 19.6MB → 約 2.9MB に圧縮、Noto Sans JP のサブセットフォントを同梱(`fonts/`)
- アイコン・ブランド周りの更新:`favicon.png`、`apple-touch-icon.png`、`logo.webp`
- スクリプト:`js/business-hours.js` を追加(営業時間判定)
- 比較用アセットの追加:`assets/*_before.webp` / `*_after.webp`、`assets/service-guide-fire.pdf`
- 動画の追加:`uploads/cleaning-panel.mp4`、`uploads/infection-panel.mp4`、`uploads/kansen-breathability-test.mp4`
