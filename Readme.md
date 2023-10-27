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




  



