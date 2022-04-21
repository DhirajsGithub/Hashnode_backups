## Git And GitHub Complete Tutorial

#In this tutorial you will be learning Git and GitHub, we will be doing it by making our local repository and will go into the advance stuff like contributing to our team repository, staging area and so on... so stay tuned !


- ### What is Git and GitHub

![687474703a2f2f312e62702e626c6f6773706f742e636f6d2f2d57593259704e72335736672f555936745a41632d4833492f414yo1414141414141424c592f784a3978337749593856382f733830302f476974687562322e706e67.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648354560096/v-zUFtGLr.png)


![1_NP_GK24IxuH89G8b3Uq5PQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648354995271/reOg97I9F.png)

You will get better understanding when we start to make a **repository**  and upload it to GitHub 

- ### What is a repositroy
In Git, a repository is a data structure that stores *metadata*(data that provides information about other data) for a set of files or **directory**(Folder/ collection of files and other sub directories) structure.

- ### Installing Git and set up the Git environment
 Go to [Git Website](https://git-scm.com/) and install it according to you Operating System.
Most often we will work in **terminal** for Mac, windows user can work in **Git bash** (for that while installing click on *use git from git bash only*) or can go with command prompt no worries. You also need to create your account at [github.com](https://github.com/)

- ### Creating You first local repository
We will go through series of command which are quite easy. Firstly we will make a directory locally --> creating a file in it --> and then using git commands, then we will deploy it to **our** GitHub repository:

    Follow the below steps to get started:

    Open your terminal or git bash or command prompt use ```
    git --version
    ```  the latest version of git is installed if it not showing make sure you install git properly.
    
- ### Some basic linux commands
For now just go through the first 7 commands for our repository to create!
    1. **Current Working Directory**  Check where you currently are using command ```pwd
    ``` 
    1. **Change Directory** change your current directory as ```
    cd 
    ``` let say to desktop then use ```
    cd Desktop
    ```. To get back to where you were us ```
    cd ..
    ``` For now don't just stay in Desktop directory
    1. ** Make a Directory** using ```
    mkdir
    ``` you can make a directory let say in Desktop directory we make ```
    mkdir demo_floder
    ```

    1.  **Make a file ** using ```
    touch
    ``` file_name change the directory from desktop to demo_folder and in it make file as ```
    touch file.txt 
    ```write any demo text in it for practise purpose.

    1. **Edit your file** using ```
    vi file.txt
    ``` use **'i'** keyword to insert text and use **'esc' + 'wq'** keyword to save changes and get exit out of it

    1. **Display the context of your file** using 
```cat file.txt
``` 
    1. **Listing** Listing all the files and sub directory in the current directory using ```
    ls
    ```  with ```
    ls -a
    ``` shows all the hidden files as well.

    1. ** Remove file / folder** ```
rm -rf filename/folder_name
``` will remove that file/ folder forcefully 

    1. **Copy file ** with ```
copy filename folder_name
``` will copy filename in folder_name folder

    1.  **Move/ Rename file** with 
```mv filename folder_name
```  will move filename to folder_name folder and with 
```mv filename filename2 
```  will rename filename to filename2

![Common-Linux-Commands.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648450778305/1dG0fkZm0.png)




Now we have a directory and a file.txt **inside** it. Now we will take the following steps to upload it in **our** GitHub repository

![git-lifecycle.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1648362825412/O1yU1d5UE.webp)


- ### Some git commands
Make sure you are currently in demo_folder

    1. 
    ```git init
    ```  **initialising** your demo_folder to git. Note you will need this command only once i.e. when we create a new repository.

    1. 
    ```git status
    ```   checks the status of the file uploaded on git hub, red colour implies file is not shared (untracked file) or whose history is not been saved yet.

    1. ```
    git add .
    ``` adds **all files** history implies red color in git status changes to green.  with 
    ```git add filename
    ```  will only add that **specific** file history 

    1. ```
    git commit -m "my first comment"
    ```  will **save the history** of files with comment name 'my first comment'. We can only comment when we make a change and add them. Note: whenever you make changes you need to commit that changes using the above command.

    1. ```
    git log
    ``` will show you all your comments and the time when they were created NOTE: it will show comment name as well as it’s hash code (which looks like this commit : **9d5e3b2b6d9a5fe41ce5143004c9d14f199bfaf1**). Every commit has different hashcode


- ### Creating online repository 

    1. Since we made our first commit it's time to push it in our GitHub repository, we will be going through 
    *staging area* and how we can *delete our comment* and *branches* later on in this tutorial itself.** 
     Make sure you had created your github account**

    2. For now open [github.com](https://github.com/) at the --> top right click on the symbol thing --> 
    click 
    on new repository --> set the repository name. or you can just click on this  [create new repository](https://github.com/new) set your repository name

    1. After creating your online repository you need to copy a link. click on the code(green in color) thing --> then copy the HTTPS part which looks like this: https://github.com/DhirajsGithub/hashnode_demo_repo.git

![Screenshot 2022-03-28 at 12.40.23 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648452122466/kF536qxYQ.png)

- ### Working with GitHub using Git commands 
From here things starts to get twisty, I will provide some links to some of the common error you gonna face so please go through this videos Coz I can't able to explain them only by writing

- ### Adding your local repository to your git hub repository. 

    1. connecting remote repository to local repository with
```git remote add origin https://github.com/DhirajsGithub/hashnode_demo_repo.git
```    Note: the https: link is which you copied from your repository.

    1. 
```git remove -v 
```  will show all the url attach to the local folder/directory for now you can see only one!

    1. ```
git push origin master
``` will save the changes made to url to master branch.The default branch name in Git is master. What this branch thing is, will cover in detail lately. 
For authentication for the first time it will ask you to add GitHub username and password (for password purpose don't use your GitHub password instead use a personal token) what is personal token just follow this 1 min video [HOW TO: Fix git fatal](https://www.youtube.com/watch?v=JCcrdW4Llm0).
Open GitHub now you will able to see a pull request being made which is nothing but your local file changes!

    1. The default branch is master If in your case it is main then change the branch via [ Compare and Pull request master has push file issue error option show in git hub Solve](https://www.youtube.com/watch?v=WCTzGrUVk5M)

Now you got the basic idea of how you can push your local repository to GitHub repository it's time to go to work on a project with your friend or your dam ass team.
let say your friend have a repository of [hashnode_demo_repo
](https://github.com/DhirajsGithub/hashnode_demo_repo) and you are suppose to contribute in it!

- ### Contributing to your team repository 

    1. You need to first **fork** your friend/team repository. What fork means it that you are adding you friends repository to your own account, so that you can make changes in it. You can fork [my repository](https://github.com/DhirajsGithub/hashnode_demo_repo)as well. To fork go to your friends GitHub account ---> the repository he has ---> click on fork. Now open you GitHub that repository will be now showing on you GitHub. We can't fork our own created repository coz it's already in our GitHub.

    1. Now we will make a clone  **from our GitHub** for that click on code--> copy the HTTPS: link of the repository. after copying that link you can go with 
```git clone https://github.com/YourGitHubUsername/hashnode_demo_repo.git
```  you will now have a repository locally with the hashnode_demo_repo or whatever you had taken clone of.
![Screenshot 2022-03-27 at 5.40.18 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648383435986/ThM8bC--c.png)

    1.  **Branch** to make changes in the file, as a good developer we make separate branch, why? we will cover it later for now to make a new branch we use ```
git branch branchname
``` by default your pointer will be towards master branch i.e. your changes will be saved to master branch to change the pointer towards our branchname branch we use 
```git checkout branchname
``` 

    1. Now you changed you branch you can change the desired part of the repository and add it with ```
git add .
``` then commit you changes using ```
git commit -m "your comment"
```

    1. Add the upstream url as we added our original/master url previously as 
```git remote add upstream https://github.com/DhirajsGithub/hashnode_demo_repo.git
```  check which url you currently have you may be having the first you created of your own repository and the second one which we added using upstream with 
```git remote -v
``` 

    1. adding the changes to our online repository which is in our GitHub as 
```git push origin branchname
```  the changes we make is in our GitHub to add this changes to our team project we make a 
**pull request** after you done with ```git push origin branchname
``` then go to you GitHub you will now have a **compare and pull request** at the top click on it --> click on **create pull request** your friend will receive a notification that you made a pull request he will scrutinize your changes then can add this changes to it's repository/project.

That's it, that's how we can make contribute to the project with Git and GitHub

![GIT2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648458117547/EyYmWSjs0.png)

- ### This branch is behind/ ahead of master branch 

1. 
You will face this in you GitHub if you are working on project, coz you are not only the one who is working on the project, there are other members too, which are making changes, so how we can add those changes to our repository of the project too.

1. Go to GitHub and click on **fetch** > then **fetch merger** or you can go in command like ```
git pull upstream master
```



- ### Some advance concepts of Git and GitHub

- ### Branch and Why we shouldn't commet on master branch

![Is-it-Bad-to-Commit-to-Master-Branch-large.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648458187840/g3rsqkbu2.png)


1. 
A **branch** in Git is simply a **lightweight movable pointer** to one of these commits. The default branch name in Git is master/main . As you start making commits, you're given a master branch that points to the last commit you made. Every time you commit, the master branch pointer moves forward automatically.   

1. 
**Uses of Branch** : Branching facilitates the development of bug fixes, the addition of new capabilities and the integration of new versions after they have been tested in isolation.

1. 
**About the main/master branch** : it’s the default branch that is being used by the people, *our code that is not finalised yet might contain some errors, that is why all the code that is not finalised yet must go to the separate branch that user is not affected hence we never comment on main branch*

1. 
If you finalise your comment by commenting on it and now you wanna merge it with the main branch so that people can see it we can you the person who created the project repository can merge your branch to master branch as git merge branchname.


- ### Pull Request 

    1. 
    Pull request: if we want to merge our branch to the project we make request. When you create your own copy, and you change in your own copy how do you make sure that this change will be visible in the main project. You will make pull request.

    1. 
    Why we need to make a pull request ? coz we can’t directly push to git push upstream branchname, coz we don’t have access to that we only have access to origin. NOTE: for every new feature or bug create new pull request/new branch, one branch can only request one pull request


- ### Staging Area
If you added a file, and. you don't want to add it you want to undo it then we can use 
```git restore --staged filename
```  NOTE: we only added that file not take a comment/ snapshot of that file 

- ### How to delete our comments
git comments are store one after the other hence if we remove any comment by copying it’s hash code(which you will get when you give command ```
git log
```) it will remove all the comment above it As you can do it with ```
git reset hash-code
```


- ### How to save changes without commenting

    1. 
    How we can store all our desire work at anyplace without making a comment of that and whenever we want it back we can have it.  The command for that: All the changes we created without using the comment we want to save them we can use ```
git stash
```   it will delete all the non added file from the folder but saved as stash. Now if we want all changes back like we want our files which are store in stash back we can use 
```git stash pop
```  
    1. 
    If we permanently want to deleted those changes that we saved as stash and we can never have them by git stash pop we can use. ```
git stash clear
```  command


- ### Squishing comments

merging all the comment into single comment  ```
git branch branchname
``` ---> ```
git checkout branchname
```  ---> (make sure your main/ master branch is uptodate before doing this) -->  ```
git rebase -i hashcode
``` ```
git log
``` for (hashcode) (of comment before that)  all comments with s (squash) and not pick and comment pick above all s, then all s will be squish into pick comment. ---> it will allow you to comment on the merged comment.
What are **merge conflicts **how to resolve them: if two individuals make a change on same lines then it is merge conflict when we merge them in master branch it will have to resolve to the leader of the project to resolve this conflict manually.


![1650558611171.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1650558759538/jjC0UDCDU.jpg)


- 
### side hustle


1. $ git rm - - cached -r .  —> will remove the added file from staging area i.e. before commit area

1. Gitignore: in your files $ touch .gitignore file must present, ls -a In .gitignore we will have all that file name which will be ignore as we add with add . And also ignore them with the commit We can also specify like *.txt in .gitignore will ignore all the files with .txt extension. 
1.  From https://github.com/github/gitignore This is GitHub's collection of .gitignore file templates. We use this list to populate the .gitignore template choosers available in the GitHub.com interface Local repository contain .git file and remote repository is Github
1. As you change the branch with git checkout branchname we can also see the changes in out local repository We can merge our branch with master branch using $ git merger branchname , but firstly make sure to checkout the master branch In out remote repository we have insight > in it we have network we can see how many branches were there 
1.  Bro working with another bro:- first fork bor’s repository then clone it to you local shit then make the desire changes then push it to your remote repository form there you will make a pull request to your bro’s repository










![why-git.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648613798064/UlP9MF6L8.png)


















