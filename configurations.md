## Installing Git

Git supports all operating systems. You can install it using command-line tools or directly download and install the setup.

|  System  |  Description |
|  ------------- |  ------------- |
|  `GNU/Linux`  | For `Debian/Ubuntu-based` operating systems use `apt-get install git`, and if you are using another `Linux-based system`, check out the complete list of installing commands [here](https://git-scm.com/download/linux). |
|  `MacOS`  |  If you have [homebrew](https://brew.sh) installed, use this command to download and install **Git**: `brew install git`. If it's not the case, check out the complete list of installing commands for `macOS` system [here](https://git-scm.com/download/mac) |
|  `Windows` | Installing **Git** on `Windows` is hassle-free. Just go to the download [page](https://git-scm.com/download/win), click on the specific `Windows` version, and download and install the setup.  |

> [!Note]
> For more reference on how to install **Git** in your operating system, check *["Git Install Tutorial"](https://www.datacamp.com/tutorial/git-install-tutorial)*

<br>

## Configuring Git

After installing **Git**, we need to set a *username* and *e-mail adress* that will be used as identification to any change made on a repository.
```
git config --global user.name "your-user-name"
git config --global user.email "your@email.com"
```

<br>

## Creating a New Project on GitHub

### Creating a new Repository

At first, go to your repositories and select the `new` icon to create a remote repository.

![new-icon](https://user-images.githubusercontent.com/102708433/195996708-dd47591d-52b6-4405-b0ff-0f650cffaeda.png)

<br>

After that, type the repository name, to this example i will use "My First Project", and add a simple description. 

It will create an empty public repository. 

<br>

![create-repo](https://user-images.githubusercontent.com/102708433/195996838-4d66f175-4df6-493d-a479-5578631cc8b4.png)

<br>

> [!IMPORTANT]
> **Don't forget to check `Add a README file` it will be used in our example.**

# 

This is how our fisr **GitHub** repository looks like.
![Captura de tela 2022-10-15 131804](https://user-images.githubusercontent.com/102708433/196002486-9cdd5e13-b2d3-4e9b-b5b9-2df4818a97a0.png)

### Cloning a GitHub Repository
Cloning a remote repository means that we are making a copy of the repository from a remote server (GitHub) to remote directory.

#### We can simply clone the repository by providing an HTTPS link. 
```
git clone your_repository_url
```

#### And the expected terminal output should be like this:
```
Cloning into 'My-First-Project'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 597 bytes | 59.00 KiB/s, done.
```

#### After cloning the remote directory from GitHub, was created in my local repository a copy of `My-First-Project`.
![Captura de tela 2022-10-15 141718](https://user-images.githubusercontent.com/102708433/195999480-16a6dc07-e5f6-458b-9b21-a6531f1b83dc.png)

---

> **Warning**
> **Before we add files to our repository, make sure you are in the correct local directory on terminal.**

```
cd repository_name
```

---

### Adding Project Files
You can add any directory, file, or data after the initial command `git add`. 

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
