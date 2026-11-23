# 組織の設定チェックリスト（Owner 向け）

github.com/organizations/Unlimited-Gear/settings で行います。左メニューの名前で書いています。

## まず最初に

- [ ] 自分の個人アカウントで **2FA（二要素認証）を有効化** し、リカバリーコードを保存する
- [ ] **Authentication security** → 「Require two-factor authentication for everyone」をオン
  - メンバーを招待する前にオンにしておくと、招待された人は 2FA を設定しないと参加できなくなります

## General

- [ ] Organization display name：`Unlimited Gear`（そのまま）
- [ ] Description：`VALORANTを中心に活動するe-Sportsチーム Unlimited Gear（ULG）の開発組織。大会運営やチーム活動を支えるツールを開発しています。`
- [ ] URL：チームの公式サイト、なければ公式 X のURL
- [ ] Social accounts：公式 X / YouTube / Twitch など、チームとして公開しているものだけ
- [ ] Location：Japan
- [ ] Email (will be public)：**誰でも見られます**。チーム用アドレス以外は入れない。迷惑メールが気になるなら空欄でも可
- [ ] Billing email（非公開）：管理者が受け取れるアドレスに

## Member privileges

- [ ] Base permissions：**Read**（メンバーは全リポジトリを閲覧のみ。書き込みはチームやリポジトリ単位で付与）
- [ ] Repository creation：Public / Private とも **オフ**（作成は Owner のみ）
- [ ] Repository forking：**オフ**
- [ ] Pages creation：Public のみ必要なら許可、なければオフ
- [ ] Admin repository permissions：
  - Repository visibility change：**オフ**
  - Repository deletion and transfer：**オフ**
  - Issue deletion：**オフ**
- [ ] Projects base permissions：**Write**（メンバーがカンバンを動かせるように）

## Repository（既定値）

- [ ] 既定のブランチ名：`main`
- [ ] 既定のラベル：[ORG_GUIDE.md](ORG_GUIDE.md) のラベル一覧を登録（以降に作るリポジトリに自動で入ります）

## Actions → General

- [ ] Workflow permissions：「Read repository contents and packages permissions」（最小権限）

## Advanced Security（Code security）

- [ ] Dependabot alerts：既存リポジトリで有効化し、「新しいリポジトリで自動的に有効」をオン
- [ ] Dependabot security updates：同上

## People / Teams

- [ ] **Teams** → `core` チームを作成（チームの開発メンバー全員）
- [ ] **People** → Invite member
  - チームのもう1人の管理者：**Owner**（Owner は2人以上にする）
  - チームの開発メンバー：**Member**、`core` チームに追加
- [ ] チーム外の協力者は組織に招待しない。各リポジトリの Settings → Collaborators and teams → Add people で **Write** を付ける
- [ ] 各リポジトリで `core` チームに **Write** を付ける

## Third-party Access

- [ ] OAuth app policy：制限あり（既定）のまま。使うアプリだけ承認する
- [ ] Claude を使う場合は [Claude GitHub App](https://github.com/apps/claude/installations/select_target) を組織にインストールし、使うリポジトリだけ選ぶ

## 無料プランの注意

- Private リポジトリでは **ブランチ保護・Rulesets が効きません**。`main` への直接 push 禁止と PR レビューは [CONTRIBUTING.md](../CONTRIBUTING.md) のルールとして運用します
- 組織レベルの Actions Secrets は Private リポジトリから使えません。リポジトリごとに設定します
