# Personal Portfolio & Blog

CV・自己紹介ページとブログ機能を備えたGitHub Pages用のJekyllサイトテンプレートです。

## 🚀 クイックスタート

### 1. リポジトリの設定
1. このリポジトリをフォークまたはテンプレートとして使用
2. リポジトリ名を `mypage` または任意の名前に設定
3. `_config.yml` でサイト情報を更新

### 2. GitHub Pages の有効化
1. リポジトリの **Settings** → **Pages** に移動
2. **Source** を「GitHub Actions」に設定
3. 自動的にサイトがビルド・デプロイされます

### 3. ローカル開発環境のセットアップ

```bash
# リポジトリをクローン
git clone https://github.com/sakanotakumi/mypage.git
cd mypage

# 依存関係をインストール
bundle install

# ローカルサーバーを起動
bundle exec jekyll serve

# ブラウザで http://localhost:4000 にアクセス
```

## 📝 カスタマイズ

### 基本情報の更新
`_config.yml` を編集：

```yaml
title: あなたの名前 - Portfolio & Blog
email: your.email@example.com
description: "あなたの説明"
baseurl: "/mypage" # リポジトリ名
url: "https://yourusername.github.io"
github_username: yourusername
```

### プロフィール画像
`assets/images/profile.jpg` に画像を配置

### ページ内容の更新
- `about.md` - 自己紹介
- `cv.md` - 履歴書・CV
- `portfolio.md` - ポートフォリオ
- `contact.md` - 連絡先

### ブログ記事の追加
`_posts/` フォルダに以下の形式でファイルを作成：

```
_posts/YYYY-MM-DD-title.md
```

## 🔧 トラブルシューティング

### 404 エラーが発生する場合

1. **GitHub Pages の設定確認**
   - Settings → Pages で「GitHub Actions」が選択されているか確認
   - Actions タブでビルドが成功しているか確認

2. **_config.yml の確認**
   ```yaml
   baseurl: "/mypage" # リポジトリ名と一致させる
   url: "https://yourusername.github.io"
   ```

3. **ファイル名の確認**
   - ファイル名は小文字で
   - スペースの代わりにハイフンを使用

4. **フロントマター の確認**
   各ページファイルの先頭：
   ```yaml
   ---
   layout: page
   title: ページタイトル
   permalink: /about/
   ---
   ```

### ローカル環境で動かない場合

```bash
# Ruby と Bundler がインストールされているか確認
ruby --version
bundler --version

# 依存関係を更新
bundle update

# キャッシュをクリア
bundle exec jekyll clean
bundle exec jekyll serve
```

## 📱 レスポンシブデザイン

- モバイルファースト設計
- タブレット・デスクトップ対応
- モダンなグリッドレイアウト

## 🎨 カスタマイズ可能な要素

- カラーテーマ（CSS変数で簡単変更）
- フォント（Google Fonts）
- レイアウト構成
- ナビゲーションメニュー

## 📁 ファイル構造

```
mypage/
├── _layouts/          # HTMLレイアウト
├── _posts/           # ブログ記事
├── assets/
│   ├── css/         # スタイルシート
│   ├── js/          # JavaScript
│   └── images/      # 画像ファイル
├── _config.yml      # サイト設定
├── index.html       # ホームページ
├── about.md         # About ページ
├── cv.md           # CV/履歴書ページ
├── portfolio.md    # ポートフォリオページ
├── blog.md         # ブログ一覧ページ
└── contact.md      # お問い合わせページ
```

## 🚀 デプロイURL

サイトは以下のURLでアクセス可能です：
```
https://sakanotakumi.github.io/mypage/
```

## 📄 ライセンス

このプロジェクトはMITライセンスの下で公開されています。
