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












