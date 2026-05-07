# Git & GitHub コマンドチートシート

今回の練習で使ったコマンドをまとめました。

---

## 1. 確認系

```bash
# Gitのバージョン確認
git --version

# リモートリポジトリの確認
git remote -v
```

---

## 2. Issue作成

```bash
# Issueを作成
gh issue create --title "タイトル" --body "説明文"
```

---

## 3. ブランチ作成

```bash
# masterを最新にしてからブランチを切る
git checkout master
git pull origin master
git checkout -b feature/issue-3-add-line3
```

---

## 4. ファイル編集後にコミット

```bash
# ステージング
git add git.txt

# コミット（Closes #番号 でIssueと紐付け）
git commit -m "Add PR Practice Line3

Closes #3"
```

---

## 5. プッシュ

```bash
git push origin feature/issue-3-add-line3
```

---

## 6. PR作成

```bash
gh pr create \
  --title "PRのタイトル" \
  --body "説明文。Closes #3 と書くとマージ時にIssueが自動クローズ" \
  --base master \
  --head feature/issue-3-add-line3
```

---

## 典型的な流れ

```
Issue作成 → ブランチ作成 → 修正 → コミット → プッシュ → PR作成 → レビュー → マージ
```

`Closes #番号` をコミットメッセージかPR本文に含めると、マージ時にIssueが自動でクローズされます。
