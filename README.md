# how-to-git

*For the git-nerds: Forgive me. The following introduction is written for people who never worked with git and I sometimes use words that might not be entirely correct.*

*This text contains funny git-words that are explained [here](https://github.com/CharliesWelt/how-to-git/new/main#some-basic-terms).*

*Git is learning by doing. You can read as many tutorials as you want, in the end you will have to try it yourself. Set up a test-repository, **mess it up** completely and try to fix it afterwards to figure out what happens with all these commands/buttons, until you feel safe.*

### What is git?
Git is an open-source software to work collaboratively on code. It is a **little** bit like a cloud (the term is distributed version control) but much cooler. For example, you will be able to track every change you (or someone else) made. You can even revert your changes or go back to a certain point in the file history where your program was still working. If several people are working on the same code, you can merge both versions afterwards without losing information. You can work on your code in private, and share it with the world when you're finished.

### Advantages of using git
- You store only one file and git does the version control for you (i.e., having one file like 'get_data.py' instead of 'get_data_v3.3_final_final2_FINAL.py'). That enhances the reproducibility and therefore the integrity of your work.
- Your work is pretty safe on a server, even if a fire destroys all your hard-drives. The usual provider of git servers also make regular backups in case anything happens to their servers. We could still argue about data protection on foreign servers, so you might want to think about that before you put sensitive information there.
- Git makes collaborative work really easy. There is nothing wrong with using it just on your own, but the moment you want to invite others to have a look at your work or contribute to it, this is done in a minute in a consistent manner without introducing confusion about who has done what, when or why.

### Disadvantages of using git
- Lots of people experience a rather steep learning curve. But there are loads of materials online and especially beginner questions are already answered several times in forums.

### Getting started in git
- Git servers:
    - The probably most famous git server is github.com. You need to get an account first.
    - The University of Twente has its own gitlab-server: https://gitlab.utwente.nl/users/sign_in. You sign in with your student/employee number and your usual password.
    - Gitlab and github work very similar. There is nothing wrong with having repositories (similar to a project folder) on both servers. If a repository should be accessible to people from outside the UT, github is the place to go to.
- Decide in which way you want to interact with the repository on the server. You will most probably not work directly on the server, but on a local (or remote) machine. That means that you have to update the server-version with your local version regularly. The classical approach is by using a command line terminal (in particular for Linux). There is also free available software which provides you with a graphical user interface. Examples of GUIs are
    - for Windows and Mac: Fork
    - for Linux: Kraken
    - Working from crib.utwente.nl: crib has some buttons for the basic operations (change the view on the left sidebar to see them) but not an advanced GUI. So for some operations you might have to switch to the website of the git server or get used to the command line. As crib runs with Linux this is pretty easy. Start a new terminal from the launcher and navigate to the repository.
- Add a new repository (recommendation: do this step on the website of the server, there you're guided through some of the settings like the visibility of the repository or choosing a licence).
- Clone the project on your local machine (this could also be crib.utwente.nl or a remote machine).
- Navigate to the local version of the repository, this should be a folder on your machine. Make a change, e.g. add a random file. At this moment, the new file exists only locally. The "synchronisation" with the server has to be done manually. To update the server-version with your local changes you need to add, commit and push them. Do that often, it adds markers in your file history where you can go back to and prevents losing information.
- When someone else (or you on another machine) made changes in the same repository on their local machine, added and committed these changes, then your local version is behind the server-version. You have to pull the changes that have been done in between to update your local folder.
- These are the very basic functionalities that provide you already with a lot of the advantages of git mentioned above and the commands that you will be using several times a day. However, there are situations where something doesn't work out as planned (and this will probably happen more often in the beginning). There's not the one easy presentable solution for every case that could happen, but there are tons of answers on the internet! However, you will have to spend some time now and then to fix your errors. The good side: You will get better soon! *For the people with impostor syndrome: Yes, there are these git-nerds that can explain you everything in sooo much detail with super terms only they understand, but I bet the majority of people uses only the basic functionalities or even avoids git at all because it sounds a bit complicated if you haven't tried it yourself yet.*

### Some basic terms

| | |
|-------|-------|
| repository | Similar to a project folder containing your code. It's good practice to not store data and binary files here, keep these separate in another place. |
| clone | The first time you download the content of the repository to your local machine. |
| fetch | Look if there are changes / new commits on the server that are not on your local machine. |
| pull | Download these changes to your local machine. |
| add | Select your local changes that you want to upload / push to the server in the following commit. |
| commit | A single contribution to the repository consisting of the added changes. You can (and should) add a commit message to explain the changes you made to help your colleages and future you to understand what happened). |
| push | Upload the changes / your commit to the repository |
| merge | Bring together two different versions of the project. This could apply for merging two changes made in the same time span by two different people (or you on two different machines...) or by merging branches. |
| branch | Can have different applications, it could for example be a working copy of the repository. That's helpful when you want to develop a functionality in peace without having to worry about messing up the main code that is already working so far. Every repository consists at least of one master branch but you can set up a new branch any time e.g. for unfinished files or things which aren't tested yet. When creating a new branch, it is at first a copy to another branch, e.g. the master branch (or to be more precise, a pointer to the state that this branch had at this point in time). |
| merge conflict | Sometimes if two people are working / pushing in the same time in the same branch, you can get a merge conflict: Git doesn't know which of both modified file versions is the right to upload to the branch. This is solved by an auto-generated branch you can merge into the remote branch with an own commit. If you are working on the same file, you may have to solve this merge conflict manually. There are several options, so that you can just compare the 2 changed files and select line-by-line which changes should be updated to the remote branch. |
| checkout | When you see a repository as a folder on your computer, the checkout-command fills this folder with the content of the respective branch. When you checkout another branch, the folder content changes. So always check in which branch you are working, before making changes. |

The cool thing about git is that nothing will be deleted. Even if you crash your program, you can look in the repository for an older version where it was still working. To be sure that everything is stored on git you have to push your local changes regularly, at least at the end of the day. Even if you didn't finished your task, you should upload it. Then you can use a working branch for unfinished files or you set up a little description message in your commit. After completing the work on this working branch you may merge it to the master branch.

### Random information
- Git is meant for text files with any type of code like scripts (but also e.g. Latex files). It is not meant for binary files. That doesn't mean that it can't handle binary files at all, but they consume more space than usual and changes will slow the system down. Therefore **store your data in a different place**. (Background: Per each commit, git saves only the changes in the text file. When you add one line, only the information of this line is saved in the context of the existing file. That's not possible for a binary file, so the entire file is stored again and again with every change which becomes a problem especially for large files.)
- Explore the web-page of gitlab/github. It provides you some useful functions, as e.g. to define the steps of your plan in issues (you can assign these issues to persons and set a deadline) or write a Wiki.

### Possible useful resources
- Github seems to have a kind of a bot that helps you getting started: https://lab.github.com/githubtraining/introduction-to-github. I didn't look into it, but maybe you can tell me afterwards if it was useful :)
