# ⏪ How to Undo the Last Git Commit (Soft Reset)

## 📌 Why?
Sometimes you commit changes by mistake or need to adjust your commit history. Instead of doing everything from scratch, Git lets you undo your last commits in a safe and flexible way. This tutorial explains how to undo one or more commits using a **soft reset** — keeping all your changes staged.

---

## ✅ **Undo the Last Commit**

To undo the last commit but **keep the changes staged**, use this command:

```bash
git reset --soft HEAD~1
```

You can replace `1` with any number to undo more than one commit. For example, to undo the last 5 commits:

```bash
git reset --soft HEAD~5
```

### 🛠️ **How It Works:**
1. `git reset` → Moves the current branch to an earlier commit.
2. `--soft` → Keeps your changes staged (ready to commit again).
3. `HEAD~5` → Tells Git to move 5 commits back.

---

### 📌 **Example Output**

**Before the reset:**
```bash
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   sd-wan-lan.md
```

**Run the soft reset:**
```bash
$ git reset --soft HEAD~5
```

**After the reset:**
```bash
$ git status
On branch main
Your branch is behind 'origin/main' by 7 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   ../06-wan/wan-backup-connectivity.md
        modified:   ../07-sd-access/sd-access-multicast.md
        new file:   sd-wan-architecture.md
        new file:   sd-wan-design.md
        new file:   sd-wan-high-availability.md
        new file:   sd-wan-lan.md
        new file:   sd-wan-onboarding.md
```

---

## 🎯 **Final Notes**
- This command is useful for reworking recent commits without losing your changes.
- After the reset, you can edit your files, recommit, or change the commit message.
- If you want to **remove the changes completely**, use `--hard` instead of `--soft` (⚠️ be careful — this will erase your changes).

Now you know how to undo commits without losing your progress! 🧠
