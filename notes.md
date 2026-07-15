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