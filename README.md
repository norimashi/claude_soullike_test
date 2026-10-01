# Petrified Grove — Web build

Godotでエクスポート済みのWeb版をGitHub Pagesで配信するためのフォルダーです。

## 公開

1. 公開用のGitHubリポジトリを用意します。GitHub FreeではPublicリポジトリを使用します。
2. このフォルダーの内容をリポジトリの直下に配置し、GitまたはGitHub Desktopでコミット・プッシュします。ブラウザーからのファイルアップロードでは、大きい`.pck`と`.wasm`を送れません。
3. GitHubの`Settings > Pages`で、Sourceを`Deploy from a branch`、Branchを公開するブランチ（通常は`main`）、フォルダーを`/(root)`に設定し、保存します。
4. Pagesのデプロイ完了後、同じ設定画面の`Visit site`からゲームを開いて動作を確認します。

`.nojekyll`はJekyllによる変換処理を無効化するための空ファイルです。Godotの実行に必要なファイルは`index.*`です。

## 更新

Godotから再エクスポートした後、公開用リポジトリ内の`index.*`を最新の書き出し一式に置き換え、コミット・プッシュします。ファイル名と相対配置を維持し、HTML・JavaScript・WASM・PCKを同じ書き出しの組み合わせで更新してください。追加ファイルが生成された場合は、そのファイルも含めます。

現在の書き出しはスレッド無効で、GDExtensionは使用していません。将来これらを有効にする場合は、クロスオリジン分離の要件を再確認してください。

## 公式資料

- [GitHub Pagesの公開元設定](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Pagesの作成と.nojekyll](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [GitHubのファイル容量制限](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github)
- [GodotのWebエクスポート](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_web.html)
