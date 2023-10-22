# Tutorial - GitHub Actions

- [GitHub Actions のクイックスタート - GitHub Docs](https://docs.github.com/ja/actions/quickstart)

## メモ

公式ドキュメント > 「最初のワークフローを作成する」はブラウザ上のみで完結する模様。

今回はリモートリポジトリを新規作成の上、次の手順で対応した。

```shell
# 作業ディレクトリを作成
mkdir tutorial-github-actions
cd tutorial-github-actions

# リポジトリの初期化
git init .

# README ファイルを作成
touch README.md

# README.md を編集後にコミット・プッシュ
git commit -m 'first commit'
git remote add origin git@github.com:kenkenpa198/tutorial-github-actions.git
git push -u origin main

# ブランチを切って YAML ファイルを作成
git switch -c octocat-patch-1
mkdir -p .github/workflows
touch .github/workflows/github-actions-demo.yml

# YAML ファイルへサンプルコードを挿入後にコミット・プッシュ
git add -vA
git commit -m 'Add GitHub Actions example'
git push origin HEAD
```

- ブランチ: [kenkenpa198/tutorial-github-actions at octocat-patch-1](https://github.com/kenkenpa198/tutorial-github-actions/tree/octocat-patch-1)
- YAML ファイル: [/.github/workflows/github-actions-demo.yml](https://github.com/kenkenpa198/tutorial-github-actions/blob/octocat-patch-1/.github/workflows/github-actions-demo.yml)

上記の操作後、下記内容が実行された。

> リポジトリ内のワークフローファイルをブランチにコミットすると、push イベントがトリガーされ、ワークフローが実行されます。

以降はドキュメント同様。
