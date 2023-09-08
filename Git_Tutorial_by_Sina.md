#Session 01.
Git is a useful tool for version control system (VCS) that is required to know if you want to be welcomed in the programming world. 
Imagine you are developing a program and you are done with version 1 and you went further on v2. Now you found a bug in your code and you want to come back to older version, in this case, you better to have a version control system which takes care of your versions and is able to help you back to previous version. It is not only for programming world, but also for everything else you need to have a record of it.
To start learning, you need to download git and install it on your computer. If you did so, by typing ‘git’ in terminal (MacOS or Linux) or PowerShell (Windows), you must see something but error.
~git   output:
 1. usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
 2.            [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
 3.            [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
 4.            [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
 5.            <command> [<args>]
 6. These are common Git commands used in various situations:
 7. start a working area (see also: git help tutorial)
 8.    clone             Clone a repository into a new directory
 9.    init              Create an empty Git repository or reinitialize an existing one
10. work on the current change (see also: git help everyday)
11.    add               Add file contents to the index
12.    mv                Move or rename a file, a directory, or a symlink
13.    restore           Restore working tree files
14.    rm                Remove files from the working tree and from the index
15.    sparse-checkout   Initialize and modify the sparse-checkout
16. examine the history and state (see also: git help revisions)
17.    bisect            Use binary search to find the commit that introduced a bug
18.    diff              Show changes between commits, commit and working tree, etc
19.    grep              Print lines matching a pattern
20.    log               Show commit logs
21.    show              Show various types of objects
22.    status            Show the working tree status
23. grow, mark and tweak your common history
24.    branch            List, create, or delete branches
25.    commit            Record changes to the repository
26.    merge             Join two or more development histories together
27.    rebase            Reapply commits on top of another base tip
28.    reset             Reset current HEAD to the specified state
29.    switch            Switch branches
30.    tag               Create, list, delete or verify a tag object signed with GPG
31. collaborate (see also: git help workflows)
32.    fetch             Download objects and refs from another repository
33.    pull              Fetch from and integrate with another repository or a local branch
34.    push              Update remote refs along with associated objects
35.  
36. 'git help -a' and 'git help -g' list available subcommands and some
37. concept guides. See 'git help <command>' or 'git help <concept>'
38. to read about a specific subcommand or concept.
39. See 'git help git' for an overview of the system.
40.  



#Session 02.
Git is a software that every time you run it looks to the files in the current directory and decide which it should do based on its criteria.
To start, we can create a directory to investigate how git works.
~ mkdir test
~ cd test
Now, we want to initialize git for this directory, so we type:
~ git init
~ ls -ltrha ( in Unix based OS)
By entering ls -ltrha, you can see a folder (“.git”) is created.
There is another important function in git which shows the latest status of our directory:
~ git status
If you type it here, you probably see the results below showing that you just initialized the git and there is no new thing.
On branch master
 
No commits yet
 
nothing to commit (create/copy files and use "git add" to track)

Let’s create an html file and see if this file is in git or not. By using ~ git status, you see this file is untracked and if you want to include it in your git, you must use ~ git add <your file>. 
‼ A point needed to be considered is that your file after changing go to STAGE situation and then by committing, they become the original file we are working on them. Every change takes the file into stage mode and then they need to be committed to be stored in the .git folder settings. 
After adding the file, if you desire to accept changes, you can enter git commit (-m ‘…’). If you are going to add a note to your commit you can use the parentheses part in your commit command. After committing, you do not see anything in the stage mode (when you are entering git status).
Now, if you put a change into your file, and entering git status, you just see it says one file is modified but it is not staged. To move it to stage you can enter:
~ git add <your file or -A>       -A is for including all files in the directory
Above line of code, put our file(s) into stage mode and ready for commit by
~ git commit -m ‘…’

#Lesson 3
There is a command named log in git that shows the history of your work:
~ git log
This command shows you history as newer commits are on top and each commit has its own exclusive code and date.
Now imagine your project is going further and you are going to add three more files to it.
~ touch page1.html page2.html page3.html
Also, using a text editor you can add texts to these files.
You probably remember that if we type git status, we see it returns you are on master branch and you have 3 untracked files. In case, we have a change in the index.html file together with creating new files, git status returns you have a modification (for index.html) and untracked files (for 3 new files).

Till the end of lesson three, we have become familiar with below commands of git:
~git init
~git status
~git add <your file(s) or -A>
~git commit -m ‘. . .’
~git log


#Lesson 4.
If you make a change in one of your files, and want to see the difference, you can use git diff <HEAD>. HEAD is showing our current situation and the command generally looks at the new changes and your current files in HEAD. 
I changed text in page1.html and we see the results.
~git diff HEAD







Now it is important to interpret the results. Diff is a Unix system command to compare two files and a/ and b/ show old and new versions, respectively. ‘---’ and ‘+++’ also show older and newer versions. In the blue line, we see it stated that it is comparing the first line of older version and 1 and 18 lines of newer versions.
You can use –-staged instead of HEAD to see the difference in files in stage mode. imagine you are not happy with the changes you have made in page1.html and you do not want to commit it, so you can use command below to eliminate it from stage step:
~ git reset page1.html
If you want to commit other changes but page1.html, you are good to use command commit.
Another command is using checkout. It is useful when we are not sure our changes are good and we want to back every changes in the file to the previous version (last commit or HEAD).
~ git checkout –- page3.html
To summary, we had commands below in this lesson:
~git diff HEAD
~git diff -–staged
~git reset <file name>
~git checkout -- <file name>

#Lesson 5:
Continuing ...
 