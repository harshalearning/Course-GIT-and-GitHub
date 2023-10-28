Why we need GIT - Open source, collabration and Forking.

Installation of GIT: It is different for all the OS, we have different commands for windows, linux and Mac.

    In our learning we will learn the commands for Windows machine.

Git Foundations: 

    GIT Architecture
    Configuring git
    Commit the local written files using GIT
    Add SSH or Http copy, to communicate with the VC tool.
    Create key-gen for first time.
    Add your files to the remote connrction.
    Pull the files to check if they are up-to date in repository.
    Push the files to VC tools.
    Creating branches to push your individual code.


GIT FOUNDATIONS:


GIT ARCHETECTURE:

    Initilize git in local folder.
    GIT is 3 tire archetecture - Localfiles, Staging area and Repository.
    Best approch: Localfiles --> Staging area --> Repository.
    GIT HUB, GIT LAB and BIT BUCKET --> Personal Favourites.

Initilizing GIT:

    We create a folder from our system directory to keep track of files we are working on, when working files we will closely look for text files in our examples (.txt).
    So the GIT keeps the track of everything for the created file, while working VS code or powershell. As we will have terminal by default in VS code we will be working on our files using VS code.

GIT Commit and LOG Messages:

    We need few commands that are mandatory while working with GIT, those are mentioned in the GITCommands file.
    For commiting a file we first need to add the file to staging directory and then commit the file, with any message, which is mandatory for understanding purpose.

GIT Checksum and SHA:

    Hashes or SHA used to move further and backer using the code.
    SHA: 40 charecter SHA-1 [0-9 and a-f]. If anything is changed , even a small change it produces a new code, which is your 40 charecter id length. 

    SHA bascially store the code of the previous commit/parent and the data, author, messages. It basically helps to get back in time. The whole is known as checksum, which is created with each commit.

Heads:It is something that always points the tip of present commit. It basically points the current place where you are, whether it is main, branch or some other file in your VScode.
HEAD ALWAYS POINTS TO THE TIP OF CURRENT BRANCH.

Deletion From Repository:

    The files in the working directory could be easily deleted, as we didn't add it to staging area and commited the file. 
    But for the files we have already added and commited, the file could be deleted using command "git rm <filename>" and commit the same file by providing appropriate comment.
    Make note, this removes the file completely from the local server, including bin. Where as when to delete the file manually by going to the folder and then commit the file, it moves particular file to the bin/trash for recovery option.

    To have the previous versioned file located at repo to local machine, we use command checkout. It basically checks the given file name in repo and replaces the existing file in local machine with the repo file.

    ********************************************     git checkout -- <filename>    ****************************************
SCENARIO:
    Lets assume we have moved to staging area and want to come back to your working directory without going to commit the file. Is that possible ? - Yes, that is possible to bring back you file in staging area to local repository/working directory.
    For the same, we use command  *********  git reset HEAD <filename>   ************

SCENARIO:
    Can we do changes(bringing back to staging/local) for the file that is already commited? 
    No, we can't. because of data integrity. Because also each commit creates checksum and SHA messages.

     but there is one exception for very last commit, because even the SHA changes but there is no further things dependent on that commit, we can change the commit. We can say amend for that.
                    ************************      git commit --amend -m "message"    ************************


Moving to Previous version:
    Assume, after continiously commiting different versions of the file, we just want to have a version that is few days ago to have some changes from there. Then you could move there by following steps 
    1) Moving to staging area using command - git checkout (place few digits of SAH) -- <filename>
    2) Check if the differences you are moving same or not - git diff --staged.
    3) Move this file to local directory - git reset HEAD <filename>.


Reset Command in GIT:
    It means we are loosing data. There are different kinds of reset.
    1) Soft - safe - It controls only repository. It points your head to the given SHA. Remove all remaining data.
    2)Mixed - default - It controls staging area and repository. It points towards another SHA and makes your staging area a copy of the repo.
    3)hard - caution - It deals with all three. It makes local directory as copy of repo.

    We have total of 3 major's here 
    1) Local
    2) Staging area
    3) Repository

How we ignore the files in GIT:
    Rather than deleting the files, we could ignore them.
    *.js - ignores all the java script files. It should be used inside the file. Along with this !app.js ignores all the files expect app.js files.
    *.mp4 - ignores all mp4 files.you need to mention it in gitignore file.

Trick:
    The GIT doen't keep a track of folder unless there is a file in it. Similar to .gitignore, now we will use .gitkeep (any name could be used), In this way we can keep track of all empty files.


GIT for team managemnet:

GIT tree listings:
    ls-tree: lists all the contents of given tree object. such as ls -a command.
    1) Full SHA-1
    2) Partial SHA-1 - go with atleat 7 for medium size project.
    3) Branch Reference
    4) Tag reference
    5) ^
    6) ~

GIT Branching:
    We mainly use this branching for different 
    1) try new ideas - To integrate new features for existing and perfectly working application. We create a branch and when we feel everything is fine, then we merge this branch with main.
    2) Collabration - Multiple teams working on same project.
    3) Merging - It is essential thing to made changes to integrate with main.
    4) Context switching - It switch rapidly and GIT is very good at it. It could be between branches or between main and branch.

    Creating new branch:
    We create a branch to work on enhancement for the existing application/file. 
    I simple words, you create a branch to work for yourself without distrubing the existing things. For this you could create your own branch and work on the required things.
    We could create a branch from existing branch also rather than creating a branch from main/master.

    SCENARIO:
    You have made some changes to the file and you have not commited those changes yet in that particular branch. Is it possible to switch thr branch?
    Yes, we can switch the branch. This could be done in 3 ways
    1) Directly switch using checkout/switch command.
    2) Add the branch code to staging area and commit it. Then move to other branch.
    3) Stash - Its kind of place to put your things for a mean while, then bring them back again.

    NOTE: Checkout has 2 functionalities
    1) switching branches
    2) moving/copying the repository to local. By getting rid of all the changes.

    Renaming and deleting branches:
    To rename the branch we use command directly.
    To delete a branch we can use the simple command git branch -d <filename> / git branch --delete <filename>.
    You can't delete a branch sitting on the same branch, so for this you have to move on to master/main or other branches to delete the specified branch.
    We also can't delete the branch unless the data in the master/main similar to branch unless you use -D in place of -d.


Branch Merging: 
    Whenever you want to merge the branch with someother branch/main. First you have to be on that branch and then use command git merge <branchname>. No need to mention the name where you want to merge as you are already on that branch and your HEAD points that branch.

Fast Forward Branching:
    This is basically which uses the same SHA (which it already has when HEAD is pointing before switching the branch to main/master) to merge with master/main, in case any commit is not done for master/main after creating branch, working on it and merging it. There are three types of merge. The Same SHA for the branch existed will be moved to the newly merged branch into main. Baically, it is moving the existing commit into main branch.
    Basically won't keep the log of it, if we need the log we need to mention no ff during merge.
    1) FF merge
    2) merge --no-ff  --> don't do FF merge
    3) merge --ff-only --> proceed with FF merge only, if it is not possible abort the merge.
    
  



