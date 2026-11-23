# 組織の運用ルール

Unlimited Gear（ULG）の GitHub 組織で、今後すべてのプロジェクトに共通するルールです。

## 1. 人と権限

| 立場 | GitHub 上の扱い | 権限 |
| --- | --- | --- |
| チーム管理者（2人以上） | 組織の **Owner** | すべて |
| チームの開発メンバー | 組織の **Member**（`core` チーム所属） | 組織の全リポジトリを閲覧、担当リポジトリは Write |
| チーム外の協力者（例：大会運営の方） | **Outside collaborator**（組織には入れない） | 関わるリポジトリだけ Write |

- Owner は **必ず2人以上**。1人だけだと、その人がログインできなくなったときに組織を誰も管理できなくなります
- チーム外の人は組織の Member にせず、リポジトリ単位で招待します。そうすると他のプロジェクトは見えません
- 抜けた人は当日中に外す（People / Collaborators から削除）。その人が触れたトークン類は再発行する

## 2. リポジトリ

- 名前は **英小文字とハイフン**（例：`ulg-tournament-bot`）。日本語名は Description に書く
- 既定は **Private**。公開して困らないものだけ Public
- リポジトリを作れるのは Owner のみ。必要になったら Owner に依頼する
- 作ったら最低限これを入れる
  - `README.md`：何のためのものか、動かし方
  - `.gitignore`：`.env` を必ず含める
  - `.env.example`：必要な環境変数の名前だけ（値は書かない）
- 各リポジトリの Settings → General で「Automatically delete head branches」をオンにする

Issue / PR テンプレート、CONTRIBUTING、SECURITY はこの `.github` リポジトリのものが自動で使われるので、各リポジトリに置く必要はありません。

## 3. タスク管理

- タスクは **Issue**、進捗は組織の **Projects**（カンバン）で管理
- Projects はプロダクトごとに1つ作り、列は `Todo / In Progress / In Review / Done`
- ストーリーマップのストーリーは「機能要望」テンプレートで Issue にする

### ラベル（全リポジトリ共通）

| ラベル | 意味 |
| --- | --- |
| `bug` | 不具合 |
| `enhancement` | 新機能・改善 |
| `task` | 作業（設定、調査など） |
| `documentation` | ドキュメント |
| `priority: high` | 優先して対応 |
| `blocked` | 他の作業や回答待ちで止まっている |
| `question` | 相談・質問 |
| `good first issue` | 新しく入った人向け |

## 4. 秘密情報

- トークン・パスワードは **コミットしない**。ローカルは `.env`、GitHub Actions はリポジトリの Secrets に置く
- 無料プランでは、組織レベルの Secrets は Private リポジトリから使えないため、**リポジトリごとに** 設定する
- 流出時の対応は [SECURITY.md](../SECURITY.md) を参照

## 5. ドキュメントと図

設計資料も各リポジトリの `docs/` で管理します。

| 図 | ツール | リポジトリに置くもの |
| --- | --- | --- |
| ストーリーマップ | Excalidraw | `.excalidraw` と書き出した `.svg` |
| ユースケース図 | PlantUML | `.puml`（と `.svg`） |
| 処理フロー | draw.io | `.drawio`（と `.svg`） |

元ファイルと画像を両方置くと、GitHub 上でそのまま見られて、あとから編集もできます。
