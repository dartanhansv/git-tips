# 🚀 How to Delete All Remote Branches at Once

## 📌 Why?
Sometimes, you need to delete multiple remote branches from your GitHub repository, but GitHub's web interface only allows deleting them **one by one**. This tutorial shows how to delete all remote branches **at once** using Git commands.

---

## ✅ **Delete All Remote Branches (Except `main` or `master`)**

By running the following command, you will delete all remote branches **except** `main` and `master`:

```bash
git branch -r | grep -v 'main\|master' | sed 's/origin\///' | xargs -I {} git push origin --delete {}
```

### 🛠️ **How It Works:**
1. `git branch -r` → Lists all remote branches.
2. `grep -v 'main\|master'` → Excludes `main` and `master` (modify this if your default branch is different).
3. `sed 's/origin\///'` → Removes the `origin/` prefix to get clean branch names.
4. `xargs -I {} git push origin --delete {}` → Deletes each branch on GitHub.

### 📌 **Example Output**
```bash
$ git branch -r | grep -v 'main\|master' | sed 's/origin\///' | xargs -I {} git push origin --delete {}
To https://github.com/dartanhansv/cisco-certifications.git
 - [deleted]         bgp-path
To https://github.com/dartanhansv/cisco-certifications.git
 - [deleted]         bgp-path-attributes
To https://github.com/dartanhansv/cisco-certifications.git
 - [deleted]         bgp-transitive
To https://github.com/dartanhansv/cisco-certifications.git
 - [deleted]         changelog
To https://github.com/dartanhansv/cisco-certifications.git
 - [deleted]         exams
To https://github.com/dartanhansv/cisco-certifications.git
 - [deleted]         fix
```

---

## 🎯 **Final Notes**
- Always double-check before running destructive commands.
- Consider backing up important branches before deletion.
- If you're unsure, list branches first with `git branch -r`.

Now, you can clean up your GitHub branches efficiently! 🚀

