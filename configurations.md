## Git Install

Git supports all operating systems. You can install it using command-line tools or directly download and install the setup.

|  System  |  Description |
|  ------------- |  ------------- |
|  `GNU/Linux`  | For `Debian/Ubuntu-based` operating systems use `apt-get install git`, and if you are using another `Linux-based system`, check out the complete list of installing commands [here](https://git-scm.com/download/linux). |
|  `MacOS`  |  If you have [homebrew](https://brew.sh) installed, use this command to download and install **Git**: `brew install git`. If it's not the case, check out the complete list of installing commands for `macOS` system [here](https://git-scm.com/download/mac) |
|  `Windows` | Installing **Git** on `Windows` is hassle-free. Just go to the download [page](https://git-scm.com/download/win), click on the specific `Windows` version, and download and install the setup.  |

<br>

> [!Note]
> For more reference on how to install **Git** in your operating system, check *["Git Install Tutorial"](https://www.datacamp.com/tutorial/git-install-tutorial)*

<br>

## Configurations

In addition to configuring a *remote repository* URL, you may also need to set global **Git** configuration options such as *username*, or *email*. The `git config` command lets you configure your **Git** installation (or an individual repository) from the command line on your terminal. This command can define everything from **user info, to preferences, to the behavior of a repository.** 

### Git Configuration Levels and Files

Git stores configuration options in three separate files, which lets you scope options to individual repositories (local), user (Global), or the entire system (system):

|  **Scope**               |   **Description**   |
|  :---                    |  ----         |       
|  `Local`                 |  By default, `git config` will write to a *local level* if no configuration option is passed. Local level configuration is applied to the context repository `git config` gets invoked in.   |
|  `Global`                |  **Global** level configuration is *user-specific*, meaning it is applied to an operating system user. **Global** configuration values are stored in a file that is located in a user's home directory.    |  
|  `System`                |  **System-level** configuration is applied across an *entire machine*. This covers all users on an operating system and all repos. The system level configuration file lives in a `git config` file off the system root path.   |  

> [!NOTE]
> Thus the order of priority for configuration levels is: **local, global, system**. This means when looking for a configuration value, **Git** will start at the local level and bubble up to the system level.

#

### Defining User Information

As you start your first project and any eventually process that you may apply on future, you first need to define the *author name* ( username ) to be used for all *commits* in the current repository. Tipically, it's used the `--global` flag to set configuration profile for the current user which will be use as a identifier of your operations.

#### Defining username
```julia
git config --global user.name "your-user-name"
```

#

#### Defining e-mail
```julia
git config --global user.email "your@email.com"
```

> [!IMPORTANT]
> The *username* and the *e-mail* defined will be used for all *commits* by the current user.

#

#### Defining shortcuts
This is a powerful utility to create custom shortcuts for commonly used *git commands*. Take an example:

```julia
git config --global alis.ci commit
```

This creates a `ci command` that you can execute as a shortcut to `git commit`.

<br>

> For more reference about git shortcuts, check: *["Git Basics - Git Aliases"](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases)*

## Example 
After installing **Git**, the first thing to do it is to define your identification settings, as discussed before. A typical initial configuration might look something like the following:

```julia
git config --global user.name "Nicholas Chiuz"
git config --global user.email "nicholas@example.com"

git config --global alias.co checkout
git config --global alias.st status
```

## Creating a Project

When it comes about creating a new *repository*, you can choose between start a new project through the command inline `git init`, or manually creating a new repository on **GitHub**. For didactic and visual purposes, let's take the second option.

### Creating a new Repository on GitHub

Go to `Your Repositories` page and select the `new` icon to create a *remote repository*.
![261873874-eb00ca2c-743b-4287-8622-a5f9caaffe6d](https://github.com/artghieri/Git-and-GitHub-Introduction/assets/102708433/6c65aaf1-d4b7-4bb1-8e5d-2d3178c9f242)

In this new section, selec the **repository name field** and type ***Git Project***. We'll be using this name to refer to our new project. 
![261873876-0d2df648-0192-44b9-9897-01dcabb465a5](https://github.com/artghieri/Git-and-GitHub-Introduction/assets/102708433/bf5deca8-99ff-4fb3-9f48-62356e3881db)

> [!IMPORTANT]
> **Don't forget to check `"Add a README file"`.**

<br>

Your *public remote repository* might look like the following:

![261871782-0dd6ae39-eb76-4e32-aa7a-75ae7853d068](https://github.com/artghieri/Git-and-GitHub-Introduction/assets/102708433/913be38e-32a9-496d-b20b-0cd64c480543)

## Clonning 

If a project has already been set up in a central repository, the clone command is the most common way for users to obtain a local development clone. `git clone` is primarily used to point to an existing repo and make a clone or copy of that repo at in a new directory, at another location.

The `git clone` command copies an existing **Git** repository making a completely isolated environment from the original repository. As a convenience, cloning automatically creates a remote connection called "origin" pointing back to the original repository. This makes it very easy to interact with a central repository.

```julia
git clone your_repository_url 
```

### Git URLs

**Git** has its own URL syntax which is used to pass remote repository locations to **Git** commands. `git clone` is most commonly used on *remote repositories* and supports a few different network protocols and corresponding URL formats. 

| **Protocol**          |     **Description**        |
| :----------:            | -------                    |
| `SSH`     | **Secure Shell (SSH)** is a authenticated network protocol that is commonly configured by default on most servers. Because SSH is an authenticated protocol, you'll need to establish credentials with the hosting server before connecting. |
| `GIT`     | A protocol unique to git. **Git** comes with a daemon that runs on port (9418). The protocol is similar to SSH however it has no authentification. |
| `HTTPS`   | **Hyper Text Transfer Protocol**. The protocol of the web, most commonly used for transferring web page HTML data over the Internet. | 

<br>

> For more reference, check the documentation *[git-clone](https://git-scm.com/docs/git-clone)*

# 

### Clonning a Remote Repository

To initialize our project, first we need to pull all files from the *remote repository* located on **GitHub**. In this case, we're clonning the *remote repository* by providing an **HTTPs** link.

```julia
git clone https://github.com/username/Git-Project
```

Succeed the cloning of the *remote directory* appointed before, it will be created in your machine a *local repository* of `Git Project`.

![image](https://github.com/artghieri/Student-Guide---The-C-Language/assets/102708433/6559093f-a95a-416d-a728-8581f212ea37)

# 

<br>

## Repository and File Modifications

When working in **Git**, the concept of "saving" is a more nuanced process than saving in a traditional file editing applications. A *commit* is the **Git** equivalent of a "save". Traditional saving should be thought of as a file system operation that is used to overwrite an existing file or write a new file. Alternatively, **Git** *committing* is an operation that acts upon a collection of files and directories.

**Git** *commits* can be captured and built up ***locally***, then pushed to a ***remote server*** as needed using the `git push -u origin main` command. 

A **Git** repository can be configured to ignore specific files or directories. This will prevent **Git** from saving changes to any ignored content. **Git** has multiple methods of configuration that manage the ignore list.

#

### Git Add

The `git add` command adds a change in the **working directory** to the **staging area**. It tells **Git** that you want to include updates to a particular file in the next *commit*. However, `git add` doesn't really affect the repository in any significant way-changes are not actually recorded until you run `git commit`.

In conjunction with these commands, you'll also need `git status` to view the state of the working directory and the staging area.

<br>

> For more reference, check the documentation : *[git-add](https://git-scm.com/docs/git-add)*

#

### Workflow

The `git add` and `git commit` commands compose the fundamental **Git** workflow. They are the means to record versions of a project into the repository’s history.

Developing a project revolves around the basic edit/stage/commit pattern. First, you edit your files in the working directory. When you’re ready to save a copy of the current state of the project, you stage changes with `git add`. After you’re happy with the staged snapshot, you *commit* it to the project history with `git commit`.

In addition to `git add` and `git commit`, a third command `git push` is essential for a complete collaborative **Git** workflow. `git push` is utilized to send the *committed* changes to *remote repositories* for collaboration. 

<br>

> For more reference, check the documentation *[git-commit](https://git-scm.com/docs/git-commit)*

<br>

## Project Modifications

Proceeding the with the work done in the previously topics, after creating a *local repository* and pull all the original files from **Git-Project** that was created in the begining, we'll add a new archive to the project.

Inside the *"Git-Project"* folder, create a `document.txt` with the following text: *My first document*. Might look like the following image:

![image](https://github.com/artghieri/Student-Guide---The-C-Language/assets/102708433/29173016-8e08-4907-bbb0-4a97f21082f2)

Open the `README.md` file and change the text for the following:

```
## Hello World

This is my *first project* using **Git** and **GitHub**.
```

# 

### Adding, Commiting and Pushing Files

After all files modifications has been made, we can *stage* all changes with the command inline `git add .`.

```julia
git add .
```

> [!NOTE]
> You can always check any changes made with `git status` command.

<br>

With `git status` command it's possible to visualize any change that has been made in the files in your *local repository*. As you can see in the expected following message:

```julia
git status
```

```julia
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   document.txt
```



#### Your directory shoud look like this
![Captura de tela 2022-10-15 150312](https://user-images.githubusercontent.com/102708433/196002551-46d64c0c-b2cc-4e02-9d29-94690e32ee90.png)


#### Use the follow command on terminal.
```
git add .
```
#### And then use the follow command on terminal.
```
git status
```

#### And the expected terminal output should be like this:
```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   textfile.txt
```

#### Now our files have been modified and staged in the local directory, needed to be ready (commited) to be upload on GitHub.

## Commit
We will commit all the changes with a simple message, and the output shows all the new files in create mode.

```
git commit -m "my first commit"
```

#### And the expected terminal output should be like this:
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
#### Now our files are ready to be upload to GitHub.

### Push
Syncing with GitHub remote repository requires a remote name and branch name `git push <remote-name> <branch-name>`. 

If you have only one remote and one branch, then using `git push` will work.   

After `git push`, the pop-up window will ask for the credentials, just add your GitHub username or password. 

[Create a Personal Acess Token](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) to use in the password field instead of your GitHub passsword.


```
git push
```


We are going to check our GitHub repository to see whether we have successfully pushed the changes to remote. 

![Captura de tela 2022-10-15 152437](https://user-images.githubusercontent.com/102708433/196002456-3c73b3ae-2208-49c5-b26d-24f7f83e9064.png)

## Branches
It is recommended to work with branches: for example, if you want to work on project documentation, create a documentation branch using `git checkout` or `git branch`. Make changes in the README file and when you have finalized the changes, merge the branch with the base.  

In our case, we have created and switched to a new branch called `project`

```
git checkout -b project
```

Open the README.md file and write on it "This is a new branch". After that,  we will stage changes and save a snapshot of changes with a message.

```
git add README.md

git commit -m "this is a commit from a different branch"
```

The remote repository doesn't have a readme branch. To create a new branch and push changes, we will use *"project"*. 

The output of the command shows that new branches have been created and both local and remote `project` branches are synced. 

```
git push origin project
```

#### This is how your GitHub should looks like
![Captura de tela 2022-10-15 154355](https://user-images.githubusercontent.com/102708433/196003059-40d6799a-8130-4815-8b63-bef4c38b6904.png)

![Captura de tela 2022-10-15 154412](https://user-images.githubusercontent.com/102708433/196003103-9d5bdf03-6f13-4549-9a15-094176b04370.png)


## Pull Request
This functionality is common for organizations. For example,  a software developer has worked on a new feature and wants to merge changes to the main remote branch. We will now create pull requests using GitHub GUI by clicking on the pull request button. 

After that, select the readme branch  which we want to merge with the base (main). You can type a detailed explanation of what features were added and click on the pull request button. 

![Captura de tela 2022-10-15 154817](https://user-images.githubusercontent.com/102708433/196003164-7d590a21-b94d-42dd-8c67-ac7f5511e556.png)

The maintainer of the repository will compare your changes and merge them when they have passed all the tests. In our case, you are the maintainer, so click on the merge request to blend changes with the main branch. 

![merge](https://user-images.githubusercontent.com/102708433/196003328-b3755345-3d5a-4640-8610-e6ad26d7c08d.png)

![merge](https://user-images.githubusercontent.com/102708433/196003333-eb117df6-70a7-4ab8-a068-a47724d183c0.png)

Congratulations, we have successfully created a pull request and merged it with the main branch. You can view the changes on the main branch here. 

![merge](https://user-images.githubusercontent.com/102708433/196003355-5e41db19-1002-47df-a1bf-df53870d6f30.png)
