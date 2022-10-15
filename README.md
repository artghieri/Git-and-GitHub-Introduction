
## What is Git?
**Git is a open source distributed version control system ( DVCS )** designed to handle everything from small to very large projects with speed and efficiency created by **Linus Torvalds ( Linux creator )**. 

In other words, Git enables you to store code, track revision history, merge code changes, and revert to earlier code version when needed, creating a colaborative environment to all his collaborators.

### How does it Work?
Git stores your files and their development history in a local repository. Whenever you save changes you have made, Git creates a commit. A commit is a snapshot of current files. These commits are linked with each other, forming a development history graph. It allows us to revert back to the previous commit, compare changes, and view the progress of the development project. The commits are identified by a unique hash which is used to compare and revert the changes made.

![git-workflow](https://user-images.githubusercontent.com/102708433/195977441-74cf5a49-dc4e-4562-8b33-edcec7b1add4.png)

#### Before we go deeper in the Git Universe, we need to establish two extremely important concepts that will be used in your future projects.

### What are Branches?
**The branches are copies of the source code that works parallel to the main version.** You can either merge these changes to the original copy or just let the branch remain independent. **This feature promotes conflict-free teamwork**. Each developer has his/her task, and by using branches, they can work on the new feature without the interference of other teammates. **Once the task is finished, you can merge new features with the main version (master branch).**

#### Before we go into using branches, I want to show you a visual representation of our repository which looks like this:

![Captura de tela 2022-10-15 062401](https://user-images.githubusercontent.com/102708433/195979205-1abb0f59-3091-4cf0-af78-e5fb4ec5259c.png)

As you can see, in our master branch were made just one modification of the original file, and i was thinking to change a considerable part of the code, but i'm not so sure that it's gonna work. To avoid any trouble, i will create a new branch to see what can happen to my code.

![Captura de tela 2022-10-15 063831](https://user-images.githubusercontent.com/102708433/195979692-b402e2a6-b832-4697-b0a7-5728455b86b2.png)

It worked!, so i merged that version allocated in the new branch to my master branch, and now the master branch has two modifications. 

### What are Commits?
**There are three states of files in Git: modified, staged, and commit.** When you make changes in a file, the changes are saved in the local directory. They are not part of the Git development history. To create a commit, you need to first stage changed files. You can add or remove changes in the staging area and then package these changes as a commit with a message describing the changes.  

#### Committed State
A file in the **committed state** means that all the changes made to the file have been saved in the local repository. That means these files are ready to be pushed to the remote repository - which means they can be uploaded on **GitHub**.

#### Modified State
A file in the **modified state** has some changes made to it but it's not yet saved. This means that the state of the file has been altered from its previous state in the **committed state.**

#### Staged State
A file in the **staged state means** it is ready to be committed. In this state, all necessary changes have been made so the next step is to move the file to the **commit state.**

![Captura de tela 2022-10-15 070702](https://user-images.githubusercontent.com/102708433/195980716-af116640-cde5-4e77-adeb-8f1462aac9b3.png)

### What are the benefits of Git?

* **Track Changes:** It allows developers to view historical changes, making an easy way to identify and fix bugs.
* **Team Collaboration:** As individuos, a collaborator can view and focus on your own task using branches, and merge the changes in the main version without any risk of losing the track of the development. In this way, promote an code review and real-time collaboration, making everyone in the same page.
* **Distributed VSC:** In a distributed system, there is no centralized file storage, allowing multiples backups from the same project.

## Collaboration with GitHub
**GitHub** is a cloud software development platform. It is commonly used for saving files, tracking changes, and collaborating on development projects. Individuals can contribute to open-source projects and bug reports, discuss new projects and discover new tools.  

### Features
**GitHub** also provides various other features that are as important as showcasing a portfolio.

* **Open-source:** GitHub provides a complete ecosystem for open-source projects. You can sponsor maintainers, contribute to a project, use the open-source tool in your existing project, and promote your work. 
* **Community Collaboration:** GitHub has become a community platform where issues, feature requests, code, and documentation contributions can be discussed. 
* **Explore:** GitHub Explore tab helps you discover new projects, trending tools, and developer events. 
* **GitHub Gists:** You can share the snippet of your code or embed it in a blog or website. 
* **GitHub CLI:** It allows you to perform merge requests, review code, check issues, and monitor progress from the command line program. 
* **Free Storage:** unlimited private and public repositories storage.
* **Web hosting:** You can publish your portfolio site or documentation. GitHub pages provide easy to build and deploy website experience. 
* **Codespace**: a cloud development environment integrated with your GitHub repository. 
* **Project:** a customizable, flexible tool for planning and tracking the work on GitHub.
* **Automation:** GitHub Action automates development workflow such as build, test, publish, release, and deployment.
* **Sponsor:** You can support your favorite open-source project or developers by paying a monthly or one-time fee. It also allows developers to use third-party payment platforms such as ko-fi. 

## Getting Started
In order to use all **Git** and **GitHub** features, we need to establish a proper development environment in your system to enable them. 

#### In this section we will learn how to install Git and configure it to acess your GitHub repository.

### Installing Git
#### Git supports all operating systems. You can install it using command-line tools or directly download and install the setup.

#### GNU/Linux
For Debian/Ubuntu-based operating systems use `apt-get install git`, and if you are using another Linux-based system, check out the complete list of installing commands [here](https://git-scm.com/download/linux).

#### MacOS
If you have [homebrew](https://brew.sh) installed, use this command to download and install Git: `brew install git`. If it's not the case, check out the complete list of installing commands for macOS system [here](https://git-scm.com/download/mac)

#### Windows
Installing Git on Windows is hassle-free. Just go to the download [page](https://git-scm.com/download/win), click on the specific Windows version, and download and install the setup. 

For more reference on how to install **Git** in your operating system, check ["Git Install Tutorial"](https://www.datacamp.com/tutorial/git-install-tutorial)

### Configuring Git

#### After installing Git, we need to set a username and email adress that will be used as identification to any change made on a repository.
```
git config --global user.name "your-user-name"
git config --global user.email "your@email.com"
```

## Starting a new Project
Let's start creating our first project on **GitHub**.

### Creating a new Repository

#### At first, go to your repositories e click on the `new` icon to create a remote repository.
![new-icon](https://user-images.githubusercontent.com/102708433/195996708-dd47591d-52b6-4405-b0ff-0f650cffaeda.png)

#### After that, type the repository name, to this example i will use "My First Project", and add a simple description. 

#### It will create an empty public repository. 
![create-repo](https://user-images.githubusercontent.com/102708433/195996838-4d66f175-4df6-493d-a479-5578631cc8b4.png)

> **Note**
> **Don't forget to check `Add a README file` it will be used in our example.**

#### This is how our fisr GitHub repository looks like.
![repo](https://user-images.githubusercontent.com/102708433/195997156-970d5e3e-842e-4c24-a72c-5626029ec42e.png)

### Cloning a GitHub Repository
Cloning a remote repository means that we are making a copy of the repository from a remote server (GitHub) to remote directory.

#### We can simply clone the repository by providing an HTTPS link. 
```
git clone your_repository_url
```

#### And the terminal output will be like this:

```
Cloning into 'My-First-Project'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 597 bytes | 59.00 KiB/s, done.
```

#### As you can see, after cloning the remote directory from GitHub, was created in my local repository a copy of it.
![Captura de tela 2022-10-15 141718](https://user-images.githubusercontent.com/102708433/195999480-16a6dc07-e5f6-458b-9b21-a6531f1b83dc.png)

---

> **Warning**
> **Before we add files to our repository, make sure you are in the correct local directory on terminal.**

```
cd repository_name
```

---

### Adding Project Files
You can add any directory, file, or data after the initial command. 

```
git add url file.file
```

> **Note**
> **There's no need for URL if the file is on the root of your local directory.**

If you want to add all files to the staging area, then use dot. 

```
git add .
```

#### Open the file README.md in your local directory with any text editor and write the follow sentence:
```
Hello, World.
This is my First Project.
```

#### Create a new textfile in the root of your local directory and write the follow sentence:
```
This is a text file.
```

#### Your directory shoul look like this
![Captura de tela 2022-10-15 150312](https://user-images.githubusercontent.com/102708433/196001578-32769090-4a91-4c36-9171-6a7a043aab98.png)

#### Use the follow command on terminal.
```
git add .
```
#### And then use the follow command on terminal.
```
git status
```

#### This is expected ouput:
```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   textfile.txt
```

#### And now we can see that our files have been modified and staged, wich means, they need to be prepare to be upload on GitHub.

## Commit
We will commit all the changes with a simple message, and the output shows all the new files in create mode.

```
git commit -m "my first commit"
```

#### This is the expected output:
```
[main 423f731] my first commit
 2 files changed, 3 insertions(+), 1 deletion(-)
 create mode 100644 textfile.txt
 ```
 
 > **Note**
 > **If you want to send to your remote server a specific commit to differents files, follow this order to each file:**
 ```
 git add url file.file
 
 git commit -m "my commit"
```

#### If you type git status again on terminal this is the expected output:
```
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
#### This means that our files are now ready to be upload to GitHub.

### Push
Syncing with GitHub remote repository requires a remote name and branch name `git push <remote-name> <branch-name>`. 

If you have only one remote and one branch, then using `git push` will work.   

After `git push`, the pop-up window will ask for the credentials, just add your GitHub username or password. 

[Create a Personal Acess Token](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) to use in the password field instead of your GitHub passsword.


```
git push
```


We are going to check our GitHub repository to see whether we have successfully pushed the changes to remote. 

![Captura de tela 2022-10-15 152437](https://user-images.githubusercontent.com/102708433/196002360-4fc7a1c6-8598-49d7-b7ca-157085b59adc.png)


## Git Cheat Sheet
#### This cheat sheet features the most important and commonly used Git commands for easy reference.



<!-- https://git-scm.com/about/branching-and-merging --!>
