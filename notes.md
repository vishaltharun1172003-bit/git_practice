# Git Learning Notes
## Raghavendra Vishal
## NTUT — UTL Lab

Version Control:
- Tracks every change in your project
- Who changed, what changed, when, why
- Can go back to any previous version
- Eliminates "final_v2_FINAL_USE_THIS" problem

Why Git:
- Created by Linus Torvalds in 2005
- Built in 10 days after BitKeeper removed free access
- Key innovation: Distributed — every developer has complete copy
- Fast, reliable, free, open source
- No single point of failure

Local vs Remote:
- Local repo: .git folder on your machine, works offline
- Remote repo: GitHub/GitLab server, accessible by team
- git push: send local changes to remote
- git pull: get remote changes to local
- git fetch: check what changed on remote

Git Three Areas:
1. Working Directory — where you edit files
2. Staging Area (Index) — where you prepare commits
3. Repository (.git/) — permanent history

Commands:
- git add    → Working Directory → Staging Area
- git commit → Staging Area → Repository
- git push   → Local Repository → Remote Repository
- git pull   → Remote Repository → Local Repository

Key insight: Staging area lets you choose exactly
what goes into each commit

vishal@Vishal:~/git_practice$ git add notes.md
vishal@Vishal:~/git_practice$ git status 
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   notes.md

vishal@Vishal:~/git_practice$ git commit -m "Initial commit: add notes.md" 
[master (root-commit) 7d90ebd] Initial commit: add notes.md
 1 file changed, 37 insertions(+)
 create mode 100644 notes.md
vishal@Vishal:~/git_practice$ git log --oneline
7d90ebd (HEAD -> master) Initial commit: add notes.md
vishal@Vishal:~/git_practice$ git log 
commit 7d90ebdcbf31a601fe5a6447900003d9dcea1809 (HEAD -> master)
Author: Raghavendra Vishal <raghvendaravishal@gmail.com>
Date:   Thu Jul 16 00:44:10 2026 +0800

    Initial commit: add notes.md
vishal@Vishal:~/git_practice$ find .git/refs -type f
.git/refs/heads/master
vishal@Vishal:~/git_practice$ find .git/objects -type f
.git/objects/9e/092f550a17492abaa9bc19de75a13ee4a41101
.git/objects/7d/90ebdcbf31a601fe5a6447900003d9dcea1809
.git/objects/7a/85e6c1bb7ff3b72c46a22a63b5195f0f25aa0c
vishal@Vishal:~/git_practice$ cat .git/refs/heads/master
7d90ebdcbf31a601fe5a6447900003d9dcea1809
vishal@Vishal:~/git_practice$ 

SHA-1 Hashing:
- Git uses SHA-1 to generate a unique 40 character ID for every object
- Same input → always same hash
- Different input → always different hash
- Cannot reverse the hash to get content back
- Git uses hash to detect any change in files
- Storage: first 2 chars = folder, remaining 38 = filename
- Why: keeps objects folder fast with millions of files
- git hash-object <file> → compute hash
- git cat-file -p <hash> → read object content
- git cat-file -t <hash> → check object type