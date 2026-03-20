# Version Tracker

Node.js の最新バージョン情報を自動で取得し、テキストファイルとして公開するリポジトリです。
GitHub Actions により定期的に更新され、GitHub Pages を通じて簡易的な Web API として利用可能です。

## 🚀 公開エンドポイント (Web API)

ブラウザやスクリプトから直接 `fetch` して利用できます。

| 内容 | URL |
| :--- | :--- |
| **Latest LTS** | [https://haiix.github.io/version-tracker/nodejs/lts.txt](https://haiix.github.io/version-tracker/nodejs/lts.txt) |
| **Latest Current** | [https://haiix.github.io/version-tracker/nodejs/current.txt](https://haiix.github.io/version-tracker/nodejs/current.txt) |

## 🛠 仕組み

1.  **自動更新**: GitHub Actions が毎日定刻（23:18 UTC）に実行されます。
2.  **データ取得**: [nodejs.org](https://nodejs.org/dist/index.json) の公式JSONから最新バージョンを抽出します。
3.  **自動保存**: バージョンに更新があった場合のみ、リポジトリ内の `nodejs/` フォルダへ自動コミット＆プッシュします。
4.  **ホスティング**: GitHub Pages を通じて、常に最新のテキストデータが配信されます。

## 📖 使い方 (JavaScript 例)

CORSに対応しているため、フロントエンドから直接呼び出すことが可能です。

```javascript
const getLtsVersion = async () => {
  const res = await fetch('[https://haiix.github.io/version-tracker/nodejs/lts.txt](https://haiix.github.io/version-tracker/nodejs/lts.txt)');
  const version = await res.text();
  console.log(`Node.js LTS: ${version.trim()}`);
};
```

## License
MIT License
