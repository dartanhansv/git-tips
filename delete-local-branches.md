# 🚀 How to Delete All Local Branches at Once

## 📌 Why?
Over time, local branches can accumulate and make your Git workspace messy. Instead of deleting them one by one, you can remove them all **at once**, except the `main` and `master` branches.

---

## ✅ **Delete All Local Branches (Except `main` and `master`)**

By running the following command, you will delete all local branches **except** `main` and `master`:

```bash
git branch | grep -v -E "main|master" | xargs git branch -d
```

### 🛠️ **How It Works:**
1. `git branch` → Lists all local branches.
2. `grep -v -E "main|master"` → Excludes both `main` and `master` branches.
3. `xargs git branch -d` → Deletes each listed merged branch.

---

### 📌 **Example Output**
```bash
$ git branch | grep -v -E "main|master" | xargs git branch -d
Deleted branch feature-1 (was a1b2c3d).
Deleted branch feature-2 (was e4f5g6h).
Deleted branch bugfix (was i7j8k9l).
Deleted branch testing (was m1n2o3p).
```

---

## 🎯 **Final Notes**
- Always check with `git branch` before deleting.
- If some branches are **not merged**, Git will warn you before deletion.
- To **force delete** unmerged branches, use `git branch -D` instead of `git branch -d`.

Now, your Git workspace is clean and organized! 🚀
