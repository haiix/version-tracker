# Open Version Tracker

各種開発ツールの最新バージョンを自動取得し、テキストファイルとして公開するリポジトリです。
GitHub Actions で定期実行し、GitHub Pages を通じて軽量な Web API (CORS対応) として提供します。

## 🚀 公開エンドポイント (Web API)

各ツールの最新バージョンをプレーンテキストで取得できます。

### Node.js
| 種類 | URL |
| :--- | :--- |
| **LTS** | [https://haiix.github.io/version-tracker/nodejs/lts.txt](https://haiix.github.io/version-tracker/nodejs/lts.txt) |
| **Current** | [https://haiix.github.io/version-tracker/nodejs/current.txt](https://haiix.github.io/version-tracker/nodejs/current.txt) |

## 🛠 仕組み

1.  **自動クロール**: GitHub Actions が公式の配布元や API から最新情報を取得します。
2.  **差分更新**: 取得したバージョンに更新がある場合のみ、リポジトリへ自動コミットします。
3.  **配信**: GitHub Pages 上でホストされるため、`curl` や `fetch` を使ってサーバーレスでデータを取得可能です。

## 📖 使い方 (JavaScript)

```javascript
// 例: Node.js の LTS バージョンを取得
const fetchVersion = async () => {
  const url = '[https://haiix.github.io/version-tracker/nodejs/lts.txt](https://user.github.io/version-tracker/nodejs/lts.txt)';
  const response = await fetch(url);
  const version = await response.text();
  console.log(`Version: ${version.trim()}`);
};
