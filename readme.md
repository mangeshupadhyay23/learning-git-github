this is a demo repo to increase git understanding

GIT
version control system,decentralized and distributive helps in managing the changes in an open source system intitally developed for linux kernal project 


COMMITS
sanapshots which keep a track of changes
a git repo consists at least a branch called master by default commits are made on the branch


GIT HUB
git hub is a git hosting platform


GIT states
1. working directory : where we work on the code
2. repository: .git folder which is shown on github
3. staging area: this area is used to prepare for next commit all commits passes through staging area before actually reflecting on github
4. fourth area(remote branch): it is basically not included in git states 



0. addig ur name and id in git 
$ git config --global user.name "Mangesh Upadhyay" 
//// if username already set u have to use a regexp, --add or --replace-all to change user.name.

<enter>

$ git config --global user.email "mshanit@gmail.com"



1. git init to initialize git repo that is creating a third stage 
$ git init
Initialized empty Git repository in C:/Users/jay/Desktop/demo/.git/

2. lets check git status
$ git status
On branch master     ////working on branch named master by default

No commits yet       ////nothing commited on timeline or branch yet

nothing to commit (create/copy files and use "git add" to track)  //// nothing in staging area as well


3. lets make a file reame.md in it

4. and then lets check status
$ git status
On branch master       

No commits yet        ////nothing commited

Untracked files:
  (use "git add <file>..." to include in what will be committed)   ////one untracked file is there which is in working directory state currently
        readme.md

nothing added to commit but untracked files present (use "git add" to track)

5. lets add this file in our git  
$ git add . (or readme.md) (. for all files)

6. now lets check status 
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)   ////a commit is in staging area not commited yet on master branch
        new file:   readme.md

7. now lets commit the change in third state or in repo or on master branch
$ git commit -m "first commit"
[master (root-commit) a70e5ce] first commit   ////we made our first commit on our master branch with the and gives us a root commit id.
 1 file changed, 1 insertion(+)               //// 1 file is chaged that is the file we created
 create mode 100644 readme.md

8. lets check status again
$ git status
On branch master   //// on master branch 
nothing to commit, working tree clean   //// nothing to commit in staging area  and no untracked file

the actual repo is stored in .git folder

9. how to delete repo in a folder
rm -rf .git
now ur repo that is .git folder is removed 

10. tracing the commit history 
$ git log
commit a70e5ce6a6fef3bf40f84c5fb4d3d10462084c2d (HEAD -> master)
Author: mangesh <mshanit@gmail.com>
Date:   Tue Apr 28 20:43:56 2020 +0530

    first commit //// comit made 

11. To know the difference between two commit and to see all the commit log
$ git show
commit a70e5ce6a6fef3bf40f84c5fb4d3d10462084c2d (HEAD -> master)
Author: mangesh <mshanit@gmail.com>
Date:   Tue Apr 28 20:43:56 2020 +0530

    first commit

diff --git a/readme.md b/readme.md
new file mode 100644
index 0000000..110042b
--- /dev/null
+++ b/readme.md
@@ -0,0 +1 @@
+this is a demo repo to increase git understanding
\ No newline at end of file


//// Lets make changes in pur readme file and check git status 
 12. check status after edit in readme
$ git status
On branch master
Changes not staged for commit:       /// git is tracking this file so theres no untracked file but changes not staged
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.md       /// here it shows modified file but not new file cause we just modified it didnt create it 
                                   

no changes added to commit (use "git add" and/or "git commit -a")

13. Express commit 
adding the file in staging area  and then directly commiting it to repo with modification 
NOTE: it only works for tracked file and not for untracked files so u need to use git add . for adding untracked files
here we only have modification in a tracked file and not in an untracked file

$ git commit -am "second commit (an express commit)"
[master 9d3ea9f] second commit (an express commit)
 1 file changed, 83 insertions(+), 1 deletion(-)
 rewrite readme.md (100%)

 14. not lets check out our git commit history
 $ git log
commit 9d3ea9fdc356034572f6e7ff8d0b972a64da3f9d (HEAD -> master)
Author: mangesh <mshanit@gmail.com>
Date:   Wed Apr 29 00:24:29 2020 +0530

    second commit (an express commit)   //// latest one is shown at the top

commit a70e5ce6a6fef3bf40f84c5fb4d3d10462084c2d
Author: mangesh <mshanit@gmail.com>
Date:   Tue Apr 28 20:43:56 2020 +0530

    first commit

15. Removing a change or commit from staging state / unstaging
lets add something rubbish in our file 
and then add it to git staging area
$ git add .
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   readme.md

now lets remove it from staging area or unstage it
$ git reset HEAD readme.md(name of file)
Unstaged changes after reset:
M       readme.md

lets check our status now
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.md

no changes added to commit (use "git add" and/or "git commit -a")
so the modification has been removed from our staging area

//but u must having noticed it that the rubbish we added is still there in our working directory we can also see this in status so how to revert to last saved state of a file stored in repo

16. Reverting the changes 
git checkout <space> (name of file)
$ git checkout -- readme.md

your file must have stored back to the last saved state in git repo
check the status 
$ git status
On branch master
nothing to commit, working tree clean

that means our working directory is upto date with our repo and there are no changes 

18. git help log 
$ git help log  // it will provide u a list or all available options but quite confusing
what if u want to search for a simplified history of all commits u made ..... lets have a look at it

19. simplified way to look at history of commits
by using multiple commands
$ git log --oneline --graph --decorate --all
* 2c77533 (HEAD -> master) third commit
* 9d3ea9f second commit (an express commit)
* a70e5ce first commit

--online => it tells u about a commit within one line not in multiple line making it easy to read
--graph => it will provide u a asterisk based graph denoting hierachy
--decorate => which commits are part of which branches
--all => which provie history of all branches in repo
better way of looking at history

20. Making your own command or alias command(a made up or assumed command)

config git for your own commands like for checking hisotry 
so the command is 
$ git config --global alias.(choose name of command) "ur set of commands"

example (i used name of command to be saga to trace history of repo)
$ git config --global alias.saga "log --online --graph --decorate --all"
u can check list of alias command by 
$ git config --global --list

using it
$ git saga
* 2c77533 (HEAD -> master) third commit
* 9d3ea9f second commit (an express commit)
* a70e5ce first commit

u can even make addition to the alias commands like 
$ git saga -- readme.md (checking history of only one file)
* 2c77533 (HEAD -> master) third commit
* 9d3ea9f second commit (an express commit)
* a70e5ce first commit


21. 




















