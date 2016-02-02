## Git & Github

Git and Github are related, but separate things.  Git is the version control software that keeps track of your html pages and other files that make up your application and Github is an online service (using git) that allows you to host your repositories on the web and explore, clone, and contribute to other software projects.

A few things to remember about using git in your projects:

### Creating and adding to your new git repository

#### 1. Whenever you create a new project, also create a new folder to hold all of the files as this will make sure that all the files exist in one location.

```zsh
$ mkdir myNewProject
$ ls
$ cd myNewProject
$ pwd
/Users/calvinwebster/projects/myNewProject
```
#### 2. Once you've navigated to your new project folder, you'll want to create a new (but empty) git repository

```zsh
$ git status
fatal: Not a git repository (or any of the parent directories): .git

$ git init
Initialized empty Git repository in /Users/calvinwebster/projects/myNewProject/.git/

$ git status
On branch master

Initial commit

nothing to commit (create/copy files and use "git add" to track)

```

#### 3. Now that you have an empty git repository, you can start creating files and writing code.  When you're at a good stopping point, go ahead and add and commit those changes to the git repository.

```zsh
$ touch index.html styles.css

$ ls
index.html styles.css

$ git status
On branch master

Initial commit

Untracked files:
(use "git add <file>..." to include in what will be committed)

index.html
styles.css

nothing added to commit but untracked files present (use "git add" to track)

$ git add .

$ git status
On branch master

Initial commit

Changes to be committed:
(use "git rm --cached <file>..." to unstage)

new file:   index.html
new file:   styles.css

$ git commit -m "my first commit message"
[master (root-commit) ac7e403] my first commit message
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 index.html
create mode 100644 styles.css

$ git status
On branch master
nothing to commit, working directory clean

```

### Adding a remote and pushing to Github

#### Once you have created a repository on your computer and are ready to `push` it to github

- First, you must create a repo on github
- Once the new repository is created, github actually gives you really great instructions on how to proceed and `git push` your repo from your computer to github.com

```sh
$ git remote add origin git@github.com:username/myNewProject.git

$ git push -u origin master

```

## Resources

[Try Github](https://try.github.io/levels/1/challenges/1)

[Setting up SSH Keys for Github](https://help.github.com/articles/generating-ssh-keys/)
