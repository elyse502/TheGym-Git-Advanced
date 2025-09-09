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

> 7. Reordering Commits:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
d7a8859 (HEAD -> main, origin/main) feat: Add challenge 6. Dropping a Commit
716fced feat: Add challenge 5. Advanced Squashing
0865d15 feat: Add challenge 4. Splitting a Commit
9c13256 Add challenge 3. Keeping History Tidy - Squashing Commits
2c2921e Add challenge 2. Editing Commit History
1031a12 Add challenge 1. Missing File Fix
758a096 chore: Create third and fourth files
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase -i --root
Successfully rebased and updated refs/heads/main.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
f4358c8 (HEAD -> main) feat: Add challenge 6. Dropping a Commit
76690c3 chore: Create third and fourth files
098088e feat: Add challenge 5. Advanced Squashing
ad46e33 feat: Add challenge 4. Splitting a Commit
9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
7e42297 Add challenge 2. Editing Commit History
03fe620 Add challenge 1. Missing File Fix
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git push --force-with-lease origin main
Enumerating objects: 21, done.
Counting objects: 100% (21/21), done.
Delta compression using up to 4 threads
Compressing objects: 100% (20/20), done.
Writing objects: 100% (20/20), 4.24 KiB | 206.00 KiB/s, done.
Total 20 (delta 7), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (7/7), done.
To https://github.com/elyse502/TheGym-Git-Advanced
 + d7a8859...f4358c8 main -> main (forced update)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 8. Cherry-Picking Commits:

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
* main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ touch test5.md && echo "This is test file 5" > test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch ft/branch
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test5.md

nothing added to commit but untracked files present (use "git add" to track)
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ cat test5.md
This is test file 5
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add test5.md && git commit -m "Implemented test 5"
[ft/branch e2c0122] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline --all
e2c0122 (ft/branch) Implemented test 5
7bcf02e (HEAD -> main, origin/main) feat: Add challenge 7. Reordering Commits
f4358c8 feat: Add challenge 6. Dropping a Commit
76690c3 chore: Create third and fourth files
098088e feat: Add challenge 5. Advanced Squashing
ad46e33 feat: Add challenge 4. Splitting a Commit
9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
7e42297 Add challenge 2. Editing Commit History
03fe620 Add challenge 1. Missing File Fix
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git cherry-pick e2c0122
[main bd4dd58] Implemented test 5
 Date: Fri Sep 5 13:35:20 2025 +0300
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline
bd4dd58 (HEAD -> main) Implemented test 5
7bcf02e (origin/main) feat: Add challenge 7. Reordering Commits
f4358c8 feat: Add challenge 6. Dropping a Commit
76690c3 chore: Create third and fourth files
098088e feat: Add challenge 5. Advanced Squashing
ad46e33 feat: Add challenge 4. Splitting a Commit
9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
7e42297 Add challenge 2. Editing Commit History
03fe620 Add challenge 1. Missing File Fix
2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls -la
total 32
drwxr-xr-x 3 elysee elysee  4096 Sep  5 13:36 .
drwxr-xr-x 3 elysee elysee  4096 Sep  4 15:46 ..
drwxr-xr-x 8 elysee elysee  4096 Sep  5 13:36 .git
-rw-r--r-- 1 elysee elysee 16323 Sep  5 13:26 README.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test1.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test2.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test3.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test4.md
-rw-r--r-- 1 elysee elysee    20 Sep  5 13:36 test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git push --force-with-lease origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 292 bytes | 73.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/elyse502/TheGym-Git-Advanced
   7bcf02e..bd4dd58  main -> main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 9. Visualizing Commit History (Bonus):

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline --graph --all
* 446e7dd (HEAD -> main, origin/main) feat: Add challenge 8. Cherry-Picking Commits
* bd4dd58 Implemented test 5
| * e2c0122 (ft/branch) Implemented test 5
|/
* 7bcf02e feat: Add challenge 7. Reordering Commits
* f4358c8 feat: Add challenge 6. Dropping a Commit
* 76690c3 chore: Create third and fourth files
* 098088e feat: Add challenge 5. Advanced Squashing
* ad46e33 feat: Add challenge 4. Splitting a Commit
* 9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
* 7e42297 Add challenge 2. Editing Commit History
* 03fe620 Add challenge 1. Missing File Fix
* 2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --graph --all --decorate --oneline
* 446e7dd (HEAD -> main, origin/main) feat: Add challenge 8. Cherry-Picking Commits
* bd4dd58 Implemented test 5
| * e2c0122 (ft/branch) Implemented test 5
|/
* 7bcf02e feat: Add challenge 7. Reordering Commits
* f4358c8 feat: Add challenge 6. Dropping a Commit
* 76690c3 chore: Create third and fourth files
* 098088e feat: Add challenge 5. Advanced Squashing
* ad46e33 feat: Add challenge 4. Splitting a Commit
* 9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
* 7e42297 Add challenge 2. Editing Commit History
* 03fe620 Add challenge 1. Missing File Fix
* 2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --graph --all --pretty=format:'%C(yellow)%h%Creset -%C(red)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
* 446e7dd - (HEAD -> main, origin/main) feat: Add challenge 8. Cherry-Picking Commits (5 minutes ago) <elyse502>
* bd4dd58 - Implemented test 5 (9 minutes ago) <elyse502>
| * e2c0122 - (ft/branch) Implemented test 5 (10 minutes ago) <elyse502>
|/
* 7bcf02e - feat: Add challenge 7. Reordering Commits (19 minutes ago) <elyse502>
* f4358c8 - feat: Add challenge 6. Dropping a Commit (22 minutes ago) <elyse502>
* 76690c3 - chore: Create third and fourth files (22 minutes ago) <elyse502>
* 098088e - feat: Add challenge 5. Advanced Squashing (22 minutes ago) <elyse502>
* ad46e33 - feat: Add challenge 4. Splitting a Commit (22 minutes ago) <elyse502>
* 9d562a7 - Add challenge 3. Keeping History Tidy - Squashing Commits (22 minutes ago) <elyse502>
* 7e42297 - Add challenge 2. Editing Commit History (22 minutes ago) <elyse502>
* 03fe620 - Add challenge 1. Missing File Fix (22 minutes ago) <elyse502>
* 2f91f5b - chore: Add initial test files (21 hours ago) <elyse502>
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git show-branch --all
! [ft/branch] Implemented test 5
 * [main] feat: Add challenge 8. Cherry-Picking Commits
  ! [origin/main] feat: Add challenge 8. Cherry-Picking Commits
---
 *+ [main] feat: Add challenge 8. Cherry-Picking Commits
 *+ [main^] Implemented test 5
+   [ft/branch] Implemented test 5
+*+ [main~2] feat: Add challenge 7. Reordering Commits
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline -10 --graph
* 446e7dd (HEAD -> main, origin/main) feat: Add challenge 8. Cherry-Picking Commits
* bd4dd58 Implemented test 5
* 7bcf02e feat: Add challenge 7. Reordering Commits
* f4358c8 feat: Add challenge 6. Dropping a Commit
* 76690c3 chore: Create third and fourth files
* 098088e feat: Add challenge 5. Advanced Squashing
* ad46e33 feat: Add challenge 4. Splitting a Commit
* 9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
* 7e42297 Add challenge 2. Editing Commit History
* 03fe620 Add challenge 1. Missing File Fix
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 10. Understanding Reflogs (Bonus):

```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git reflog
5b9864e (HEAD -> main, origin/main) HEAD@{0}: commit: feat: Add challenge 9. Visualizing Commit History (Bonus)
446e7dd HEAD@{1}: commit: feat: Add challenge 8. Cherry-Picking Commits
bd4dd58 HEAD@{2}: cherry-pick: Implemented test 5
7bcf02e HEAD@{3}: checkout: moving from ft/branch to main
e2c0122 (ft/branch) HEAD@{4}: commit: Implemented test 5
7bcf02e HEAD@{5}: checkout: moving from main to ft/branch
7bcf02e HEAD@{6}: commit: feat: Add challenge 7. Reordering Commits
f4358c8 HEAD@{7}: rebase (finish): returning to refs/heads/main
f4358c8 HEAD@{8}: rebase (pick): feat: Add challenge 6. Dropping a Commit
76690c3 HEAD@{9}: rebase (pick): chore: Create third and fourth files
098088e HEAD@{10}: rebase (pick): feat: Add challenge 5. Advanced Squashing
ad46e33 HEAD@{11}: rebase (pick): feat: Add challenge 4. Splitting a Commit
9d562a7 HEAD@{12}: rebase (pick): Add challenge 3. Keeping History Tidy - Squashing Commits
7e42297 HEAD@{13}: rebase (pick): Add challenge 2. Editing Commit History
03fe620 HEAD@{14}: rebase (pick): Add challenge 1. Missing File Fix
2f91f5b HEAD@{15}: rebase: fast-forward
72a77c5 HEAD@{16}: rebase (start): checkout 72a77c5d49570648986587fcd7a702be64a7954b
d7a8859 HEAD@{17}: reset: moving to origin/main
d7a8859 HEAD@{18}: rebase (abort): returning to refs/heads/main
9c13256 HEAD@{19}: rebase (start): checkout HEAD~3
d7a8859 HEAD@{20}: reset: moving to origin/main
d7a8859 HEAD@{21}: rebase (abort): returning to refs/heads/main
d7a8859 HEAD@{22}: reset: moving to origin/main
ddd5363 HEAD@{23}: rebase (continue): feat: Add challenge 6. Dropping a Commit
9c13256 HEAD@{24}: rebase (start): checkout HEAD~3
d7a8859 HEAD@{25}: commit: feat: Add challenge 6. Dropping a Commit
716fced HEAD@{26}: rebase (finish): returning to refs/heads/main
716fced HEAD@{27}: rebase (start): checkout HEAD~2
1c823f5 HEAD@{28}: commit: Unwanted commit
716fced HEAD@{29}: reset: moving to origin/main
69dbead HEAD@{30}: rebase (finish): returning to refs/heads/main
69dbead HEAD@{31}: rebase (start): checkout HEAD~2
69dbead HEAD@{32}: rebase (finish): returning to refs/heads/main
69dbead HEAD@{33}: rebase (pick): Unwanted commit
0865d15 HEAD@{34}: rebase (start): checkout HEAD~2
552e6e5 HEAD@{35}: commit: Unwanted commit
716fced HEAD@{36}: commit: feat: Add challenge 5. Advanced Squashing
0865d15 HEAD@{37}: rebase (finish): returning to refs/heads/main
0865d15 HEAD@{38}: rebase (pick): feat: Add challenge 4. Splitting a Commit
9c13256 HEAD@{39}: rebase (pick): Add challenge 3. Keeping History Tidy - Squashing Commits
2c2921e HEAD@{40}: rebase (pick): Add challenge 2. Editing Commit History
1031a12 HEAD@{41}: rebase (pick): Add challenge 1. Missing File Fix
758a096 HEAD@{42}: rebase (squash): chore: Create third and fourth files
5d9f969 HEAD@{43}: rebase (start): checkout HEAD~6
29a8fe3 HEAD@{44}: commit: feat: Add challenge 4. Splitting a Commit
d413b1f HEAD@{45}: rebase (finish): returning to refs/heads/main
d413b1f HEAD@{46}: rebase (pick): Add challenge 3. Keeping History Tidy - Squashing Commits
05b9c4c HEAD@{47}: rebase (pick): Add challenge 2. Editing Commit History
9d312e8 HEAD@{48}: rebase (pick): Add challenge 1. Missing File Fix
41cc2a7 HEAD@{49}: commit: chore: Create fourth file
5d9f969 HEAD@{50}: commit: chore: Create third file
2f91f5b HEAD@{51}: reset: moving to HEAD~
556dfc2 HEAD@{52}: rebase: fast-forward
2f91f5b HEAD@{53}: rebase (start): checkout HEAD~4
82499c5 HEAD@{54}: commit: Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 HEAD@{55}: reset: moving to HEAD~1
b16d6ca HEAD@{56}: commit: Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 HEAD@{57}: rebase (finish): returning to refs/heads/main
0cb5d63 HEAD@{58}: rebase (pick): Add challenge 2. Editing Commit History
c5b1637 HEAD@{59}: rebase (pick): Add challenge 1. Missing File Fix
556dfc2 HEAD@{60}: rebase (pick): chore: Create third and fourth files
2f91f5b HEAD@{61}: rebase (squash): chore: Add initial test files
fe51ebe HEAD@{62}: rebase: fast-forward
5322e8e HEAD@{63}: rebase (start): checkout 5322e8e2a1094d8955ff81266bec60978501f2c7
bbc473a HEAD@{64}: rebase (abort): returning to refs/heads/main
fe51ebe HEAD@{65}: rebase (start): checkout HEAD~4
bbc473a HEAD@{66}: commit: Add challenge 2. Editing Commit History
c110252 HEAD@{67}: rebase (finish): returning to refs/heads/main
c110252 HEAD@{68}: rebase (pick): Add challenge 1. Missing File Fix
187d282 HEAD@{69}: rebase (pick): chore: Create third and fourth files
ec77dd8 HEAD@{70}: rebase (reword): chore: Create second file
37dde50 HEAD@{71}: rebase: fast-forward
fe51ebe HEAD@{72}: rebase (start): checkout HEAD~3
28b142d HEAD@{73}: commit: Add challenge 1. Missing File Fix
b01b46d HEAD@{74}: reset: moving to HEAD~1
dd0f5b9 HEAD@{75}: commit: Add challenge 1. Missing File Fix
b01b46d HEAD@{76}: commit (amend): chore: Create third and fourth files
c47594d HEAD@{77}: commit: chore: Create third and fourth files
37dde50 HEAD@{78}: commit: chore: Create another file
fe51ebe HEAD@{79}: commit (initial): chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git reflog show main
5b9864e (HEAD -> main, origin/main) main@{0}: commit: feat: Add challenge 9. Visualizing Commit History (Bonus)
446e7dd main@{1}: commit: feat: Add challenge 8. Cherry-Picking Commits
bd4dd58 main@{2}: cherry-pick: Implemented test 5
7bcf02e main@{3}: commit: feat: Add challenge 7. Reordering Commits
f4358c8 main@{4}: rebase (finish): refs/heads/main onto 72a77c5d49570648986587fcd7a702be64a7954b
d7a8859 main@{5}: commit: feat: Add challenge 6. Dropping a Commit
716fced main@{6}: rebase (finish): refs/heads/main onto 0865d158c8f0befb95c030858ef2cc448fe40bbc
1c823f5 main@{7}: commit: Unwanted commit
716fced main@{8}: reset: moving to origin/main
69dbead main@{9}: rebase (finish): refs/heads/main onto 0865d158c8f0befb95c030858ef2cc448fe40bbc
552e6e5 main@{10}: commit: Unwanted commit
716fced main@{11}: commit: feat: Add challenge 5. Advanced Squashing
0865d15 main@{12}: rebase (finish): refs/heads/main onto 2f91f5b6e3dabaee0b4d4770444da66fdf4fa555
29a8fe3 main@{13}: commit: feat: Add challenge 4. Splitting a Commit
d413b1f main@{14}: rebase (finish): refs/heads/main onto 2f91f5b6e3dabaee0b4d4770444da66fdf4fa555
82499c5 main@{15}: commit: Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 main@{16}: reset: moving to HEAD~1
b16d6ca main@{17}: commit: Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 main@{18}: rebase (finish): refs/heads/main onto 5322e8e2a1094d8955ff81266bec60978501f2c7
bbc473a main@{19}: commit: Add challenge 2. Editing Commit History
c110252 main@{20}: rebase (finish): refs/heads/main onto fe51ebe770362b12fc398a8a1b0470e46b75a559
28b142d main@{21}: commit: Add challenge 1. Missing File Fix
b01b46d main@{22}: reset: moving to HEAD~1
dd0f5b9 main@{23}: commit: Add challenge 1. Missing File Fix
b01b46d main@{24}: commit (amend): chore: Create third and fourth files
c47594d main@{25}: commit: chore: Create third and fourth files
37dde50 main@{26}: commit: chore: Create another file
fe51ebe main@{27}: commit (initial): chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git reflog show ft/branch
e2c0122 (ft/branch) ft/branch@{0}: commit: Implemented test 5
7bcf02e ft/branch@{1}: branch: Created from HEAD
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git reflog show --date=iso HEAD
5b9864e (HEAD -> main, origin/main) HEAD@{2025-09-05 13:47:53 +0300}: commit: feat: Add challenge 9. Visualizing Commit History (Bonus)
446e7dd HEAD@{2025-09-05 13:41:00 +0300}: commit: feat: Add challenge 8. Cherry-Picking Commits
bd4dd58 HEAD@{2025-09-05 13:36:24 +0300}: cherry-pick: Implemented test 5
7bcf02e HEAD@{2025-09-05 13:35:28 +0300}: checkout: moving from ft/branch to main
e2c0122 (ft/branch) HEAD@{2025-09-05 13:35:20 +0300}: commit: Implemented test 5
7bcf02e HEAD@{2025-09-05 13:34:21 +0300}: checkout: moving from main to ft/branch
7bcf02e HEAD@{2025-09-05 13:26:53 +0300}: commit: feat: Add challenge 7. Reordering Commits
f4358c8 HEAD@{2025-09-05 13:23:10 +0300}: rebase (finish): returning to refs/heads/main
f4358c8 HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): feat: Add challenge 6. Dropping a Commit
76690c3 HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): chore: Create third and fourth files
098088e HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): feat: Add challenge 5. Advanced Squashing
ad46e33 HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): feat: Add challenge 4. Splitting a Commit
9d562a7 HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): Add challenge 3. Keeping History Tidy - Squashing Commits
7e42297 HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): Add challenge 2. Editing Commit History
03fe620 HEAD@{2025-09-05 13:23:10 +0300}: rebase (pick): Add challenge 1. Missing File Fix
2f91f5b HEAD@{2025-09-05 13:21:00 +0300}: rebase: fast-forward
72a77c5 HEAD@{2025-09-05 13:21:00 +0300}: rebase (start): checkout 72a77c5d49570648986587fcd7a702be64a7954b
d7a8859 HEAD@{2025-09-05 13:19:49 +0300}: reset: moving to origin/main
d7a8859 HEAD@{2025-09-05 13:19:36 +0300}: rebase (abort): returning to refs/heads/main
9c13256 HEAD@{2025-09-05 13:16:41 +0300}: rebase (start): checkout HEAD~3
d7a8859 HEAD@{2025-09-05 13:14:21 +0300}: reset: moving to origin/main
d7a8859 HEAD@{2025-09-05 13:14:16 +0300}: rebase (abort): returning to refs/heads/main
d7a8859 HEAD@{2025-09-05 13:13:24 +0300}: reset: moving to origin/main
ddd5363 HEAD@{2025-09-05 13:12:25 +0300}: rebase (continue): feat: Add challenge 6. Dropping a Commit
9c13256 HEAD@{2025-09-05 13:11:49 +0300}: rebase (start): checkout HEAD~3
d7a8859 HEAD@{2025-09-05 13:03:58 +0300}: commit: feat: Add challenge 6. Dropping a Commit
716fced HEAD@{2025-09-05 13:00:38 +0300}: rebase (finish): returning to refs/heads/main
716fced HEAD@{2025-09-05 13:00:38 +0300}: rebase (start): checkout HEAD~2
1c823f5 HEAD@{2025-09-05 12:59:44 +0300}: commit: Unwanted commit
716fced HEAD@{2025-09-05 12:58:11 +0300}: reset: moving to origin/main
69dbead HEAD@{2025-09-05 12:56:16 +0300}: rebase (finish): returning to refs/heads/main
69dbead HEAD@{2025-09-05 12:56:16 +0300}: rebase (start): checkout HEAD~2
69dbead HEAD@{2025-09-05 12:55:09 +0300}: rebase (finish): returning to refs/heads/main
69dbead HEAD@{2025-09-05 12:55:09 +0300}: rebase (pick): Unwanted commit
0865d15 HEAD@{2025-09-05 12:55:09 +0300}: rebase (start): checkout HEAD~2
552e6e5 HEAD@{2025-09-05 12:54:17 +0300}: commit: Unwanted commit
716fced HEAD@{2025-09-05 12:49:37 +0300}: commit: feat: Add challenge 5. Advanced Squashing
0865d15 HEAD@{2025-09-05 12:45:34 +0300}: rebase (finish): returning to refs/heads/main
0865d15 HEAD@{2025-09-05 12:45:34 +0300}: rebase (pick): feat: Add challenge 4. Splitting a Commit
9c13256 HEAD@{2025-09-05 12:45:34 +0300}: rebase (pick): Add challenge 3. Keeping History Tidy - Squashing Commits
2c2921e HEAD@{2025-09-05 12:45:34 +0300}: rebase (pick): Add challenge 2. Editing Commit History
1031a12 HEAD@{2025-09-05 12:45:34 +0300}: rebase (pick): Add challenge 1. Missing File Fix
758a096 HEAD@{2025-09-05 12:43:39 +0300}: rebase (squash): chore: Create third and fourth files
5d9f969 HEAD@{2025-09-05 12:43:39 +0300}: rebase (start): checkout HEAD~6
29a8fe3 HEAD@{2025-09-05 12:38:03 +0300}: commit: feat: Add challenge 4. Splitting a Commit
d413b1f HEAD@{2025-09-05 12:33:07 +0300}: rebase (finish): returning to refs/heads/main
d413b1f HEAD@{2025-09-05 12:33:07 +0300}: rebase (pick): Add challenge 3. Keeping History Tidy - Squashing Commits
05b9c4c HEAD@{2025-09-05 12:33:07 +0300}: rebase (pick): Add challenge 2. Editing Commit History
9d312e8 HEAD@{2025-09-05 12:33:07 +0300}: rebase (pick): Add challenge 1. Missing File Fix
41cc2a7 HEAD@{2025-09-05 12:32:59 +0300}: commit: chore: Create fourth file
5d9f969 HEAD@{2025-09-05 12:32:38 +0300}: commit: chore: Create third file
2f91f5b HEAD@{2025-09-05 12:31:53 +0300}: reset: moving to HEAD~
556dfc2 HEAD@{2025-09-05 12:30:59 +0300}: rebase: fast-forward
2f91f5b HEAD@{2025-09-05 12:30:59 +0300}: rebase (start): checkout HEAD~4
82499c5 HEAD@{2025-09-04 17:23:42 +0300}: commit: Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 HEAD@{2025-09-04 17:22:14 +0300}: reset: moving to HEAD~1
b16d6ca HEAD@{2025-09-04 17:18:22 +0300}: commit: Add challenge 3. Keeping History Tidy - Squashing Commits
0cb5d63 HEAD@{2025-09-04 17:13:23 +0300}: rebase (finish): returning to refs/heads/main
0cb5d63 HEAD@{2025-09-04 17:13:23 +0300}: rebase (pick): Add challenge 2. Editing Commit History
c5b1637 HEAD@{2025-09-04 17:13:23 +0300}: rebase (pick): Add challenge 1. Missing File Fix
556dfc2 HEAD@{2025-09-04 17:13:23 +0300}: rebase (pick): chore: Create third and fourth files
2f91f5b HEAD@{2025-09-04 17:08:05 +0300}: rebase (squash): chore: Add initial test files
fe51ebe HEAD@{2025-09-04 17:07:24 +0300}: rebase: fast-forward
5322e8e HEAD@{2025-09-04 17:07:24 +0300}: rebase (start): checkout 5322e8e2a1094d8955ff81266bec60978501f2c7
bbc473a HEAD@{2025-09-04 17:06:29 +0300}: rebase (abort): returning to refs/heads/main
fe51ebe HEAD@{2025-09-04 17:04:32 +0300}: rebase (start): checkout HEAD~4
bbc473a HEAD@{2025-09-04 16:33:26 +0300}: commit: Add challenge 2. Editing Commit History
c110252 HEAD@{2025-09-04 16:25:23 +0300}: rebase (finish): returning to refs/heads/main
c110252 HEAD@{2025-09-04 16:25:23 +0300}: rebase (pick): Add challenge 1. Missing File Fix
187d282 HEAD@{2025-09-04 16:25:23 +0300}: rebase (pick): chore: Create third and fourth files
ec77dd8 HEAD@{2025-09-04 16:23:45 +0300}: rebase (reword): chore: Create second file
37dde50 HEAD@{2025-09-04 16:23:45 +0300}: rebase: fast-forward
fe51ebe HEAD@{2025-09-04 16:23:45 +0300}: rebase (start): checkout HEAD~3
28b142d HEAD@{2025-09-04 16:07:40 +0300}: commit: Add challenge 1. Missing File Fix
b01b46d HEAD@{2025-09-04 16:06:45 +0300}: reset: moving to HEAD~1
dd0f5b9 HEAD@{2025-09-04 16:04:00 +0300}: commit: Add challenge 1. Missing File Fix
b01b46d HEAD@{2025-09-04 15:52:52 +0300}: commit (amend): chore: Create third and fourth files
c47594d HEAD@{2025-09-04 15:48:28 +0300}: commit: chore: Create third and fourth files
37dde50 HEAD@{2025-09-04 15:48:20 +0300}: commit: chore: Create another file
fe51ebe HEAD@{2025-09-04 15:48:13 +0300}: commit (initial): chore: Create initial file
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br /><hr /><br />

### Part 2: Branching Basics (10 Challenges)
> 1. Feature Branch Creation:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
* main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
* ft/new-feature
  main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 2. Working on the Feature Branch:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch ft/new-feature
nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
* ft/new-feature
  main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ echo "This is the core functionality for the new feature." > feature.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls
README.md  feature.txt  part-1.md  test1.md  test2.md  test3.md  test4.md  test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ cat feature.txt
This is the core functionality for the new feature.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add feature.txt && git commit -m "Implemented core functionality for new feature"
[ft/new-feature 9d3ddce] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log -1
commit 9d3ddcea58532d0534bd748d8af59716c88d38f2 (HEAD -> ft/new-feature)
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Mon Sep 8 11:05:57 2025 +0300

    Implemented core functionality for new feature
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 3. Switching Back and Making More Changes:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
* ft/new-feature
  main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls
README.md  part-1.md  test1.md  test2.md  test3.md  test4.md  test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ echo "This is the introductory content for the project." > readme.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls
README.md  part-1.md  readme.txt  test1.md  test2.md  test3.md  test4.md  test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git add readme.txt && git commit -m "Updated project readme"
[main c535432] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log -1
commit c53543286f043e108a779cd98ad867cfc249b697 (HEAD -> main)
Author: elyse502 <elyseniyibizi502@gmail.com>
Date:   Mon Sep 8 11:24:38 2025 +0300

    Updated project readme
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 5. Branch Deletion:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
  ft/new-feature
* main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was 9d3ddce).
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 606 bytes | 303.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/elyse502/TheGym-Git-Advanced
   fa0cea7..86e383b  main -> main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 6. Creating a Branch from a Commit:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline -3
3ad0642 (HEAD -> main, origin/main)  feat: Add challenge 5. Branch Deletion
86e383b Merge branch 'ft/new-feature'
fa0cea7  feat: Add challenge 4. Local vs. Remote Branches
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git checkout -b ft/new-branch-from-commit HEAD~2
Switched to a new branch 'ft/new-branch-from-commit'
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline -3
86e383b (HEAD -> ft/new-branch-from-commit) Merge branch 'ft/new-feature'
fa0cea7  feat: Add challenge 4. Local vs. Remote Branches
2f4acc7  feat: Add challenge 3. Switching Back and Making More Changes
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
* ft/new-branch-from-commit
  main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch --all
  ft/branch
* ft/new-branch-from-commit
  main
  remotes/origin/main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 7. Branch Merging:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
  ft/new-branch-from-commit
* main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch -vv
  ft/branch                 e2c0122 Implemented test 5
  ft/new-branch-from-commit 86e383b Merge branch 'ft/new-feature'
* main                      cf8ed39 [origin/main]  feat: Add challenge 6. Creating a Branch from a Commit
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git merge ft/new-branch-from-commit
Already up to date.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 8. Branch Rebasing:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch -vv
  ft/branch                 e2c0122 Implemented test 5
  ft/new-branch-from-commit 86e383b Merge branch 'ft/new-feature'
* main                      3297f55 [origin/main]  feat: Add challenge 7. Branch Merging
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git pull origin main
From https://github.com/elyse502/TheGym-Git-Advanced
 * branch            main       -> FETCH_HEAD
Already up to date.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline --graph --all
* 3297f55 (HEAD -> ft/new-branch-from-commit, origin/main, main)  feat: Add challenge 7. Branch Merging
* cf8ed39  feat: Add challenge 6. Creating a Branch from a Commit
* 3ad0642  feat: Add challenge 5. Branch Deletion
*   86e383b Merge branch 'ft/new-feature'
|\
| * 9d3ddce Implemented core functionality for new feature
* | fa0cea7  feat: Add challenge 4. Local vs. Remote Branches
* | 2f4acc7  feat: Add challenge 3. Switching Back and Making More Changes
* | c535432 Updated project readme
* | 6a3226e  feat: Add challenge 2. Working on the Feature Branch
* | d4b2a84  feat: Add challenge 1. Feature Branch Creation
|/
* 0144dc9 docs: document part 1 git history refinement challenges
* a5876c3 feat: Add challenge 10. Understanding Reflogs (Bonus)
* 5b9864e feat: Add challenge 9. Visualizing Commit History (Bonus)
* 446e7dd feat: Add challenge 8. Cherry-Picking Commits
* bd4dd58 Implemented test 5
| * e2c0122 (ft/branch) Implemented test 5
|/
* 7bcf02e feat: Add challenge 7. Reordering Commits
* f4358c8 feat: Add challenge 6. Dropping a Commit
* 76690c3 chore: Create third and fourth files
* 098088e feat: Add challenge 5. Advanced Squashing
* ad46e33 feat: Add challenge 4. Splitting a Commit
* 9d562a7 Add challenge 3. Keeping History Tidy - Squashing Commits
* 7e42297 Add challenge 2. Editing Commit History
* 03fe620 Add challenge 1. Missing File Fix
* 2f91f5b chore: Add initial test files
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />

> 9. Renaming Branches:
```console
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
  ft/new-branch-from-commit
* main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git switch ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch -m ft/improved-branch-name
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch
  ft/branch
* ft/improved-branch-name
  main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch -r
  origin/ft/branch
  origin/main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git branch -a
  ft/branch
* ft/improved-branch-name
  main
  remotes/origin/ft/branch
  remotes/origin/main
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ git log --oneline -3
3297f55 (HEAD -> ft/improved-branch-name)  feat: Add challenge 7. Branch Merging
cf8ed39  feat: Add challenge 6. Creating a Branch from a Commit
3ad0642  feat: Add challenge 5. Branch Deletion
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$ ls -la
total 80
drwxr-xr-x 3 elysee elysee  4096 Sep  9 11:17 .
drwxr-xr-x 3 elysee elysee  4096 Sep  4 15:46 ..
drwxr-xr-x 8 elysee elysee  4096 Sep  9 11:17 .git
-rw-r--r-- 1 elysee elysee 46548 Sep  9 11:17 README.md
-rw-r--r-- 1 elysee elysee    52 Sep  9 11:12 feature.txt
-rw-r--r-- 1 elysee elysee  4066 Sep  9 11:12 part-1.md
-rw-r--r-- 1 elysee elysee  2433 Sep  9 11:12 part-2-local_vs_remote-branches.md
-rw-r--r-- 1 elysee elysee    50 Sep  9 11:12 readme.txt
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test1.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test2.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test3.md
-rw-r--r-- 1 elysee elysee     0 Sep  5 13:23 test4.md
-rw-r--r-- 1 elysee elysee    20 Sep  5 13:36 test5.md
elysee@DESKTOP-73EL1TL:~/the-gym-uok/3-sprint/advanced-git/TheGym-Git-Advanced$
```

<br />
















