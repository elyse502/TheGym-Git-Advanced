# Advanced Git Exercises
## Challenges:
### Part 1: Refining Git History (10 Challenges)
> 1. Missing File Fix:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git$ git clone https://github.com/elyse502/TheGym-Git-Advanced.git
Cloning into 'TheGym-Git-Advanced'...
cswarning: You appear to have cloned an empty repository.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git$ cd TheGym-Git-Advanced/
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ touch test{1..4}.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls
test1.md  test2.md  test3.md  test4.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test1.md && git commit -m "chore: Create initial file"
[main (root-commit) fe51ebe] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test2.md && git commit -m "chore: Create another file"
[main 37dde50] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main c47594d] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log
commit c47594dfb4e9ffaf9a90987b5b2be53acea8342d (HEAD -> main)
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 15:48:28 2025 +0300

    chore: Create third and fourth files

commit 37dde504b520764e2219c7de687f5e1fe7e33dac
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 15:48:20 2025 +0300

    chore: Create another file

commit fe51ebe770362b12fc398a8a1b0470e46b75a559
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 15:48:13 2025 +0300

    chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
c47594d (HEAD -> main) chore: Create third and fourth files
37dde50 chore: Create another file
fe51ebe chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test4.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git commit --amend
[main b01b46d] chore: Create third and fourth files
 Date: Thu Sep 4 15:48:28 2025 +0300
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 2. Editing Commit History:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log
commit 28b142da24ba2fcaec82f8d6973375f9f347c280 (HEAD -> main, origin/main)
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 16:07:40 2025 +0300

    Add challenge 1. Missing File Fix

commit b01b46dffe18ae32ba2c373c4846240b88e80bb0
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 15:48:28 2025 +0300

    chore: Create third and fourth files

commit 37dde504b520764e2219c7de687f5e1fe7e33dac
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 15:48:20 2025 +0300

    chore: Create another file

commit fe51ebe770362b12fc398a8a1b0470e46b75a559
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Thu Sep 4 15:48:13 2025 +0300

    chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
28b142d (HEAD -> main, origin/main) Add challenge 1. Missing File Fix
b01b46d chore: Create third and fourth files
37dde50 chore: Create another file
fe51ebe chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase -i HEAD~3
[detached HEAD ec77dd8] chore: Create second file
 Date: Thu Sep 4 15:48:20 2025 +0300
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
c110252 (HEAD -> main) Add challenge 1. Missing File Fix
187d282 chore: Create third and fourth files
ec77dd8 chore: Create second file
fe51ebe chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 3. Keeping History Tidy - Squashing Commits:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
bbc473a (HEAD -> main, origin/main) Add challenge 2. Editing Commit History
c110252 Add challenge 1. Missing File Fix
187d282 chore: Create third and fourth files
ec77dd8 chore: Create second file
fe51ebe chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline | wc -l
5
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase -i --root
[detached HEAD 2f91f5b] chore: Add initial test files
 Date: Thu Sep 4 15:48:13 2025 +0300
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
0cb5d63 (HEAD -> main) Add challenge 2. Editing Commit History
c5b1637 Add challenge 1. Missing File Fix
556dfc2 chore: Create third and fourth files
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git push --force-with-lease origin main
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (11/11), 2.06 KiB | 421.00 KiB/s, done.
Total 11 (delta 4), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (4/4), done.
To https://github.com/elyse502/TheGym-Git-Advanced
 + bbc473a...0cb5d63 main -> main (forced update)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />









