# 📘 Git Learning Log – Day 1

## 🚀 Overview

Today I explored core Git concepts related to **branching, merging, submodules, and repository structure**, along with debugging common issues.

---

## 🔑 Key Concepts Learned

### 1. 🧭 Git Internals (`.git` folder)

* `HEAD` → Points to current branch
* `config` → Stores repo settings (user, email, remotes)
* `objects/` → Stores all Git data (commits, blobs, trees)
* `refs/` → Stores branch and tag pointers
* `description` → Optional metadata

---

### 2. 🌿 Branching Behavior

* Branches are **pointers to commits**, not separate folders
* Uncommitted files exist in the **working directory**, not in branches
* Switching branches does NOT remove untracked files

---

### 3. ⚠️ Tracked vs Untracked Files

* **Tracked** → Added & committed → branch-specific
* **Untracked** → Not committed → visible across branches

---

### 4. 🔁 Merge Workflow

* Merging opens a **merge message editor (Vim)**
* To complete merge:

  ```
  Esc → :wq → Enter
  ```
* To abort merge:

  ```
  git merge --abort
  ```

---

### 5. ❌ Nested Repository Issue

* Running `git clone` inside a repo creates a **nested repo**
* Git treats it as a **submodule (gitlink)**

**Symptoms:**

* Folder shows as a link in GitHub
* Cannot open files normally

---

### 6. 🔗 Submodule Behavior

* Stores only a **pointer to another repo**
* Does NOT store actual files
* Identified by mode `160000`

---

### 7. 🛠️ Fixing Submodule Mistake

Convert to normal folder:

```
git rm --cached <folder>
rm -rf <folder>/.git
git add <folder>
git commit -m "convert to normal folder"
```

---

### 8. 🧹 Branch Management

* Delete local branch:

  ```
  git branch -d branch_name
  ```
* Force delete:

  ```
  git branch -D branch_name
  ```
* Delete remote:

  ```
  git push origin --delete branch_name
  ```

---

### 9. ⚙️ Git Errors Debugging

* `fatal: protocol 'https' is not supported`
  → Caused by broken Git installation
  → Fix: reinstall Git properly

---

## 🧠 Key Takeaways

* Git tracks **commits, not files directly**
* Branches are lightweight pointers
* Avoid cloning inside a repo
* Understand difference between:

  * Normal folder
  * Submodule
  * Nested repo

---

## 🎯 Next Steps

* Learn **rebase vs merge**
* Practice resolving **merge conflicts**
* Explore **GitHub workflows**

---

## 📌 Summary

Today focused on strengthening **Git fundamentals and debugging real issues**, especially understanding how Git internally manages repositories and branches.

---
