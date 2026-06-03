# npm / GitHub Packages ガイド

このリポジトリをテーマとして公開・利用する際の手順を、プログラミング未経験者向けに説明します。

## npm とは？

npm は、JavaScript の部品を配布・管理する仕組みです。

このリポジトリは「テーマの部品」として npm で扱えるようにしています。

## GitHub Packages とは？

GitHub Packages は、プライベートな npm の公開先です。

つまり、外部に公開せずに、社内やチームだけでテーマを共有できます。

## 何を設定したか

### 1. `.npmrc`

- `@your-org:registry=https://npm.pkg.github.com`
- これは `@your-org` という名前のパッケージを GitHub Packages から取る、という意味です。

### 2. `publishConfig`

- `package.json` の中に `publishConfig` を入れました。
- これはこのテーマを publish するときの公開先を指定するための設定です。

### 3. GitHub Actions の `publish.yml`

- `v*.*.*` というタグを付けて GitHub に push すると、自動で公開処理が動きます。
- GitHub の仕組みが、自動的に npm にテーマを送ります。

## テーマを公開する手順

1. テーマの変更をすべて保存する
2. `npm version patch` を実行する
3. `git push --follow-tags` を実行する

これで GitHub Actions が動き、テーマが公開されます。

## インストールする側の準備

利用する側のリポジトリでは、以下のように設定します。

### A. `package.json`

```json
{
  "devDependencies": {
    "@your-org/slidev-theme-company": "~0.1.0"
  }
}
```

### B. `~/.npmrc` にトークンを追加する

GitHub Packages からテーマを受け取るには、本人確認のための「トークン」が必要です。

次のように `~/.npmrc` に書きます。

```ini
//npm.pkg.github.com/:_authToken=ghp_xxxxxxxxxxxxxxxxxxxx
```

> トークンは他の人に見せないでください。

## まとめ

- このリポジトリは npm のパッケージとして使えるテーマです。
- GitHub Packages を使うと、社内で安全に共有できます。
- 利用する側は `package.json` にテーマを追加して、スライドで `theme:` を指定します。
