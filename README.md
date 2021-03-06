# GitHub Tutorial

_by David Gonzalez_

---
## Git vs. GitHub

<p align="center">
  <img src="images-for-github-tutorial/Git.png">
</p>

<p align="center">
  <img src="images-for-github-tutorial/Github.jpg">
</p>
  

_**Pictures are property of Git and Github**_  

[**Git**](https://git-scm.com/) was initially released on _April 7, 2005_ by its creator _Linus Torvalds_. It is a service that manages multiple versions of `code`. Any directory with git in it is a repository. Any git repository can be uploaded to github. [**Github**](https://github.com) was initially released on _April 10, 2008_ by its creator _Tom Preston-Werner_. It is a cloud drive where repositories live. Git does **not** need Github to work.



---
## Initial Setup

### Creating A Github Account:
1. Go on [**github.com**](https://github.com).
2. Click **Sign Up** in the top right corner of the window.

    <p align="center">
      <img src ="images-for-github-tutorial/sign-in-or-sign-up.PNG">
    </p>

3. Follow all the steps for step 1.

    <p align="center">
      <img src ="images-for-github-tutorial/step1-signup.png">
    </p>

4. Follow all the step for step 2 by checking whichever plan you want and checking the boxes on the bottom as you please.

    <p align="center">
      <img src ="images-for-github-tutorial/step2.PNG">
    </p>

5. Follow alll the directions in step 3, but it is not necesarry to fill it out because you can just skip it by pressing `skip this step` at the bottom.

    <p align="center">
      <img src ="images-for-github-tutorial/step3.PNG">
    </p>

### SSH Keys:

In your git workflow you most likely will type commands such as `git push` or `git push -u origin master`. The commands stated will push the most recent commit in your local repository to your remote repository on github. If you do not have an ssh key setup you will have to type in your username and password everytime you want to push and or do anything else that involves a remote repository on github.  

#### **To Create An _SSH Key_ follow the following steps:**
**_The following steps are for c9 and github.com only. If you are using your computers bash or terminal click on the video below_**

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/H5qNpRGB7Qw/0.jpg)](https://www.youtube.com/watch?v=H5qNpRGB7Qw)


1. Go on [github.com](https://github.com)

2. Click your profile icon in the top right and click on settings.

3. On the left hand side you should see the following:
* Click on the **SSH and GPG keys tab**

    <p align="center">
        <img src ="images-for-github-tutorial/github-ssh.PNG">
    </p>

4. Then go on [c9.io](https://c9.io) and sign in to your account if you are not signed in already.

5. Click on the gear icon on the top right

6. Click on the SSH Keys tab on the left side of the window as shown in the picture below.

    <p align="center">
      <img src ="images-for-github-tutorial/c9-ssh.PNG">
    </p>

7. Copy the chunk of text that is private.

8. Go back on github and click the button that is shown below as an image.

    <p align="center">
      <img src ="images-for-github-tutorial/new-ssh-key-github.PNG">
    </p>
  
9. You should now see this on your screen:

    <p align="center">
      <img src ="images-for-github-tutorial/ssh-key-form-github.PNG">
    </p>
  
10. Give the ssh key a relevant title such as cloud9 and paste the key you copied from c9 into the form's Key input box.

11. Click on Add SSH key.

12. Go to your c9 workspace and type the following into the terminal:  

    `ssh -T git@github.com`

13. The follwing should then pop up:

    ```bash
    Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access._
    ```

14. You are now done with setting up and creating a ssh key.

---
## Repository Setup

### Creating a Repository and your first git commands:

When creating your first repository, the first command you should type into the terminal, if you do not have a directory to become a repositiory, is `mkdir <insert repository name here`. After that, the next command you type into the bash is `git init`. This comand initializes git in the current directory that you are in. You should then create a **README.md** file by typing `touch README.md` into the terminal and type some stuff in the README file so that people who visit your repository on Github know what its about. After that, type in `git add .` to the bash and or another form of `git add` depending on what you have in your repository and what you want to add to the staging area and commit. To learn more about **git add**, visit [https://www.atlassian.com/git/tutorials/saving-changes](https://www.atlassian.com/git/tutorials/saving-changes). Then, type `git commit -m ""`. In the quotes type in a message in the present tense such as:  

**Initialize repository**  
This command takes a snapshot of everything you have in the staging area.
### Creating a remote repository and connecting it to your local repository:

* Go on [github.com](https://github.com)
* Click the plus icon in the top right corner.
* A dropdown menu should appear. Click on New repository.
* The following should pop up:

    <p align="center">
      <img src ="images-for-github-tutorial/remote-repository-step1-github.PNG">
    </p>

* Fill out all the information as you please and then click Create repository.

* You will be brought to the next step of creating a remote repository and connecting it to your local repository.

* Make sure that SSH is checked under **Quick setup — if you’ve done this kind of thing before**

* Copy and paste the commands into the bash that are under, **or push an existing repository from the command line** or copy the link that is next to the SSH setting and follow the following sub bulllets:
  * Type the following into the bash `git remote add origin <link here>`
  * Then type in: `git push -u origin master`

---
## Workflow & Commands

To test out your changes to your repository you should always type the following into the command line `git add`, `git status`, `git commit`, and `git push`.  

**`git push`** was referenced in the last section of the tutorial, but the last section did not state what the command does. The command pushes your local changes to your remote repository online.  

**`git status`** tells the user what files are in the staging area and which are not.

---
## Rolling Back Changes

### Rolling Back an Edit:

`git checkout -- <filename>`

### Unstaging Something From The Staging Area:

`git reset HEAD <filename>`

### Undoing A Commit

`git reset --soft HEAD~1`

### Undoing A Push To A Certain Commit:

1. Type in `git log` and you will see your previous commits. These are called SHA keys.

2. Copy the SHA you want to revert back to and type `git revert <sha>`