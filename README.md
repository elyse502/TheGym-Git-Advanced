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







