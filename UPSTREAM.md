# 跟随上游更新（upstream）

本仓库是 `Ckxkx/account-atlas` 的 fork。上游代码更新时：

```bash
git fetch upstream
git checkout main
git merge upstream/main        # main 只跟踪上游，不写自己的功能
git push origin main

git checkout feat/tokens
git rebase main                # 自己的 Toki 改动分支跟上去
# 解决冲突后：git rebase --continue
git push -u origin feat/tokens
```

Tokens 模块的改动集中在：
- 新增：`tokens.js`
- 挂接：`index.html`（tab/section/script）、`styles.css`（样式）、`app.js`（少量白名单/render/导入导出）

上游若改动这些文件的相同行，rebase 时会有小冲突，按上面策略解决即可。
