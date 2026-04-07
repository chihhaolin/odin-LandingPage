執行以下完整的 Git + GitHub + GitHub Pages 部署流程。每個步驟先檢查狀態，再決定是否需要執行。

## Step 1 — 確認目前工作目錄

確認目前在專案根目錄（含 index.html 的目錄）。

## Step 2 — Git 初始化（若尚未初始化）

執行以下指令檢查是否已有 git repo：
```
git rev-parse --git-dir 2>/dev/null
```
- 若**無** git repo → 執行 `git init`，再執行 `git branch -M main`
- 若**已有** → 跳過

## Step 3 — 確認 GitHub 遠端 remote（若尚未設定）

執行以下指令檢查是否已有 origin remote：
```
git remote get-url origin 2>/dev/null
```
- 若**無 remote** → 使用 `gh` CLI 建立 GitHub repo 並設定 remote：
  1. 先用 `gh auth status` 確認已登入 GitHub
  2. 詢問使用者想用的 repo 名稱（預設：`odin-LandingPage`）和是否要設為 public（預設：public）
  3. 執行：`gh repo create <repo-name> --public --source=. --remote=origin`
- 若**已有 remote** → 顯示 remote URL，跳過建立步驟

## Step 4 — 詢問 commit message

在執行 git add / commit 之前，先詢問使用者：
> 請輸入 commit message（直接按 Enter 使用預設訊息 "Update landing page"）：

使用使用者提供的訊息，若為空則使用預設值。

## Step 5 — Stage、Commit、Push

依序執行：
```
git add .
git status
git commit -m "<使用者的 commit message>"
git push -u origin main
```
- 若 push 失敗（例如遠端有衝突）→ 提示使用者，並建議 `git pull --rebase` 後重試，不要自動強制 push

## Step 6 — 啟用 GitHub Pages（首次）或確認已啟用

執行以下指令確認 Pages 是否已啟用：
```
gh api repos/{owner}/{repo}/pages 2>/dev/null
```
- 若**尚未啟用** → 執行：
  ```
  gh api repos/{owner}/{repo}/pages \
    --method POST \
    -f build_type=legacy \
    -f "source[branch]=main" \
    -f "source[path]=/"
  ```
- 若**已啟用** → 顯示目前 Pages URL，跳過

其中 `{owner}` 和 `{repo}` 請用以下指令取得：
```
gh repo view --json owner,name --jq '"\(.owner.login)/\(.name)"'
```

## Step 7 — 顯示結果

完成後，顯示：
- Commit hash（`git rev-parse --short HEAD`）
- GitHub repo URL
- GitHub Pages URL（格式：`https://<owner>.github.io/<repo>/`）
- 提示：GitHub Pages 首次部署通常需等待 1～2 分鐘才會生效
