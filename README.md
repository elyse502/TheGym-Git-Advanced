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

> 4. Splitting a Commit:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
82499c5 (HEAD -> main, origin/main) Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 Add challenge 2. Editing Commit History
c5b1637 Add challenge 1. Missing File Fix
556dfc2 chore: Create third and fourth files
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase -i HEAD~4
Stopped at 556dfc2...  chore: Create third and fourth files
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git reset HEAD~
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
interactive rebase in progress; onto 2f91f5b
Last command done (1 command done):
   edit 556dfc2 chore: Create third and fourth files
Next commands to do (3 remaining commands):
   pick c5b1637 Add challenge 1. Missing File Fix
   pick 0cb5d63 Add challenge 2. Editing Commit History
  (use "git rebase --edit-todo" to view and edit)
You are currently editing a commit while rebasing branch 'main' on '2f91f5b'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test3.md; git commit -m "chore: Create third file"
[detached HEAD 5d9f969] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test4.md; git commit -m "chore: Create fourth file"
[detached HEAD 41cc2a7] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase --continue
Successfully rebased and updated refs/heads/main.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
d413b1f (HEAD -> main) Add challenge 3. Keeping History Tidy - Squashing Commits
05b9c4c Add challenge 2. Editing Commit History
9d312e8 Add challenge 1. Missing File Fix
41cc2a7 chore: Create fourth file
5d9f969 chore: Create third file
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git push --force-with-lease origin main
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (13/13), 2.66 KiB | 124.00 KiB/s, done.
Total 13 (delta 6), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/elyse502/TheGym-Git-Advanced
 + 82499c5...d413b1f main -> main (forced update)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 5. Advanced Squashing:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
29a8fe3 (HEAD -> main, origin/main) feat: Add challenge 4. Splitting a Commit
d413b1f Add challenge 3. Keeping History Tidy - Squashing Commits
05b9c4c Add challenge 2. Editing Commit History
9d312e8 Add challenge 1. Missing File Fix
41cc2a7 chore: Create fourth file
5d9f969 chore: Create third file
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase -i HEAD~6
[detached HEAD 758a096] chore: Create third and fourth files
 Date: Fri Sep 5 12:32:38 2025 +0300
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
0865d15 (HEAD -> main) feat: Add challenge 4. Splitting a Commit
9c13256 Add challenge 3. Keeping History Tidy - Squashing Commits
2c2921e Add challenge 2. Editing Commit History
1031a12 Add challenge 1. Missing File Fix
758a096 chore: Create third and fourth files
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git push --force-with-lease origin main
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 4 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (14/14), 3.20 KiB | 468.00 KiB/s, done.
Total 14 (delta 7), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (7/7), done.
To https://github.com/elyse502/TheGym-Git-Advanced
 + 29a8fe3...0865d15 main -> main (forced update)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 6. Dropping a Commit:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ touch unwanted.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ echo "This is an unwanted file" > unwanted.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add unwanted.txt && git commit -m "Unwanted commit"
[main 1c823f5] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
1c823f5 (HEAD -> main) Unwanted commit
716fced (origin/main) feat: Add challenge 5. Advanced Squashing
0865d15 feat: Add challenge 4. Splitting a Commit
9c13256 Add challenge 3. Keeping History Tidy - Squashing Commits
2c2921e Add challenge 2. Editing Commit History
1031a12 Add challenge 1. Missing File Fix
758a096 chore: Create third and fourth files
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
716fced (HEAD -> main, origin/main) feat: Add challenge 5. Advanced Squashing
0865d15 feat: Add challenge 4. Splitting a Commit
9c13256 Add challenge 3. Keeping History Tidy - Squashing Commits
2c2921e Add challenge 2. Editing Commit History
1031a12 Add challenge 1. Missing File Fix
758a096 chore: Create third and fourth files
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls -la
total 24
drwxr-xr-x 3 elysee elysee  4096 Sep  5 13:00 .
drwxr-xr-x 3 elysee elysee  4096 Sep  4 15:46 ..
drwxr-xr-x 8 elysee elysee  4096 Sep  5 13:00 .git
-rw-r--r-- 1 elysee elysee 12093 Sep  5 12:58 README.md
-rw-r--r-- 1 elysee elysee     0 Sep  4 17:08 test1.md
-rw-r--r-- 1 elysee elysee     0 Sep  4 17:08 test2.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 12:30 test3.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 12:43 test4.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />








