# slidev-theme

このリポジトリは Slidev 用の共通テーマ package の雛形です。

## 目的

- テーマを各スライド repo にコピーせずに単一ソース化する
- `@your-org/slidev-theme-company` のような private npm package として管理する
- Slidev の `theme:` でパッケージ名を指定して利用できるようにする

## 使い方

### ローカルで確認

```bash
npm install
npm run dev
```

テーマリポジトリ内の `slides.md` は `theme: ./` を使ったデモです。

### Slidev から利用する例

利用側の `package.json` に以下を追加します。

```json
{
  "devDependencies": {
    "@your-org/slidev-theme-company": "~0.1.0",
    "@slidev/cli": "^0.53.0"
  }
}
```

利用側スライドの先頭では次のように指定します。

```md
---
theme: "@your-org/slidev-theme-company"
---
```

## 構成

- `layouts/` - Slidev のレイアウトを定義するディレクトリ
- `components/` - Slidev から利用できる共通コンポーネント
- `styles/` - テーマ用の CSS
- `slides.md` - テーマ確認用デモ
- `.github/workflows/publish.yml` - GitHub Packages へ publish するワークフロー
- `.npmrc` - GitHub Packages の registry 設定

## publish

タグを付けて push すると GitHub Actions で publish されます。

```bash
npm version patch
git push --follow-tags
```

---

> `.npmrc` に `NODE_AUTH_TOKEN` を直書きしないでください。
