# Version Control and Git as Fundamentals for Cloud Engineering
## Introduction to Version Control

For the cloud engineers knowing and understanding Git is essential for managing Infrastructure as code (IaC), version control and collaboration. Version control is an essential tool in modern software development, enabling developers to manage, track, and collaborate on code efficiently. It ensures the ability to revert changes, understand code evolution, and collaborate seamlessly without overwriting others' work. 
Version control systems (VCS) primarily serve two roles:
* Change tracking allows to identify who made changes, when, and why. This is a critical aspect for debugging and understanding project history.
* Collaboration allows multiple contributors to work on the same project simultaneously.

Version control systems are categorized into three types:

* Local VCS stores file copies on a single machine. It is basic and lacks collaborative capabilities.
* Centralized VCS stores all versioned files on a central server, making collaboration easier (e.g., Subversion).
* Distributed VCS, when each user has a full repository copy, offering better collaboration and redundancy (e.g., Git).

Cloud engineers should follow certain best practices while utilizing version control. Some of them are:
* Keep the repository organized with frequent updates and cleanup.
* Write clear and descriptive commit messages.
* Commit changes frequently to avoid large, complex updates.
* Use branches for feature development, bug fixes, and experiments.

Git is the most popular distributed version control system, providing a decentralized approach to managing repositories. Unlike centralized systems, Git allows each user to work independently with a complete repository copy. Developers can create branches, commit changes, and merge them back into the main codebase after review.

Besides understanding the importance of the version control, and Git itself,there are some main concepts that cloud engineers should grasp:
* Repository is a a database storing the complete history of project files and revisions. There are two types of the repositories:
    * Local: a git repository on your machine.
    * Remote: a shared repository (e.g., on GitHub, GitLab, or Bitbucket) that teams collaborate on.
* Commit is a snapshot of files at a specific time with an accompanying message describing the changes.
* Branch is a parallel version of the repository for developing features, fixing bugs, or experimenting safely, without affecting the main codebase.
* Merging integrates changes from one branch into another.
* Conflicts happen when multiple people edit the same file and Git cannot resolve the differences automatically.
* Commit history. Git maintains a history of commits (changes), which helps trace and debug code changes over time.
* Collaboration tools, such as pull requests (PRs) and forking. Pull requests are the mechanism for reviewing and approving changes before merging them into the main branch. Forking is making a copy of someone else's repository to contribute to it.

Let's understand the difference between the Git and GitHub. Git, as was pointed above, is the tool for version control, and GitHub is a platform that hosts Git repositories for collaboration and sharing. GitHub uses Git as its underlying version control technology. Cloud engineers use Git to manage their code locally and push (upload) or pull (download) changes to / from GitHub repositories. GitHub offers some additional features, such as issue tracking, pull requests, and collaboration tools, making it easier for teams to work together on projects.  

## Git Commands and Git Flow Fundamentals

The best way to know and be comfortable with the above terminology is practicing and experimenting with different Git commands. Among multiple Git commands, there are some that you, as a cloud engineer, will encounter probably the most. Here are key commands cloud engineers should know: 

Basic commands:
* `git init` – Initialize a new Git repository.
* `git clone <repo_url>` – Clone a remote repository to your local machine.
* `git status` – Show the status of your working directory and staged changes.
* `git add <file>` or `git add .` – Stage changes to be committed.
* `git commit -m "<message>"` – Commit staged changes with a message.
* `git log` – View the commit history.

Branching and merging:
* `git branch` – List branches.
* `git branch <branch_name>` – Create a new branch.
* `git checkout <branch_name>` – Switch to another branch.
* `git merge <branch_name>` – Merge another branch into your current branch.
* `git pull` – Fetch changes from a remote repository and merge them into your branch.

Working with remote repositories:
* `git remote -v` – Show remote repository URLs.
* `git push origin <branch_name>` – Push your branch to the remote repository.
* `git fetch` – Retrieve changes from the remote repository but do not merge them.
* `git pull origin <branch_name>` – Fetch and merge changes from the remote branch.

Undoing changes:
* `git reset <file>` – Unstage a file.
* `git checkout -- <file>` – Discard changes to a file in your working directory.
* `git revert <commit_hash>` – Undo a commit by creating a new commit.

Collaboration and pull requests:
* `git push` – Push your local commits to the remote repository.
Create a pull request in platforms like GitHub to propose changes.

Some advanced commands:
* `git stash` – Save changes temporarily without committing.
* `git cherry-pick <commit_hash>` – Apply specific commits from one branch to another.
* `git rebase` – Reapply commits on top of another branch (use with caution).

By mastering these Git concepts and commands, you’ll streamline your workflow and improve collaboration on cloud engineering projects. As a cloud professional you will experience the importance of knowing and being comfortable with these commands, as you will:
* version-control Terraform, CloudFormation, and other configuration files for the Infrastructure as Code (IaC).
* collaborate with teams on shared repositories for cloud projects.
* use Git as a tool that is often integrated into the Continuous Integration/Continuous Deployment (CI/CD) pipelines for the automated testing and deployment.
* debug by using a commit history to identify and fix configuration issues or code bugs.

Let's try to understand the basics of the Git flow, which should serve as a starting point, guidance to use Git on your own while practicing cloud engineering projects. Git flow is essentially about making commits locally, pushing your work to the remote, and pulling changes from others while using branches to keep tasks organized. 

**Step 1. Initializing a Git repository** is like creating a folder where Git will track all your project files and changes. Set up a local directory for the repository:
```
mkdir project-directory
cd project-directory
```
Run the following command in your project folder to initialize Git: `git init`. After this step Git is ready to track your files and changes.

**Step 2. Adding the files to the repository.** To let Git know you want to track files in your project (like code, images, or documents), you need to "add" them by running the following command: `git add .` Note, that ` .` means "add everything in this folder."

**Step 3. Committing the changes.** A commit is like taking a snapshot of your work. It saves the current state of your files in Git. Create a commit with a clear message describing the changes by running the following command: `git commit -m "<Commit message>"`.

**Step 4. Create a remote repository.** A remote repository is an online version of your project (it could be on GitHub, GitLab, or Bitbucket), that allows you to back up your work and collaborate with others. After creating a repository (let say GitHub), copy the repository's URL.

**Step 5. Connect your local repository to the remote.** by linking your local project to the remote repository and adding the remote repository URL by running the following command: `git remote add origin <repository-URL>`.

**Step 6. Push your code to the remote repository**, which means to send your local code to the remote repository so others can see it or so it's backed up. Run the following command: `git push -u origin main`, which will upload your changes to the main branch of the remote repository.

**Step 7. Making changes and committing.** After you've pushed your initial code, you might need to make changes or add new features. Add the updated files to the staging area by running `git add .`, commit the changes `git commit -m "Added a new feature"`.

**Step 8. Pull changes from the remote repository.** When you are working as a team member, others might also push their changes to the remote repository. You need to pull these changes to stay up to date by running `git pull origin main`.

**Step 9. Push the changes.** After pulling and ensuring everything works, push your new changes to the remote repository by running `git push origin main`.

While working with a team, you may use **branches**. These are like separate workspaces to work on different tasks without affecting the main project. For the branching Git flow, you will need to follow these steps:

**Step 1. Create a new branch** for your task by running: `git branch feature/new-feature`.

**Step2. Switch to the branch** by running `git checkout feature/new-feature`.

**Step 3. Work on the branch:** add commits here and follow the necessary steps described above.

**Step 4. Merge to main,** once the feature is done, by running the following command:

```
git checkout main
git merge feature/new-feature
```
### Setting Up SSH Access to GitHub

One of the useful steps that you would need to follow while organizing your work with Git and GitHub is setting up SSH access to the GitHub. Using SSH keys with GitHub enables secure access to repositories without repeatedly entering credentials. Here is the simplified process to set up SSH keys (using macOS):
1. Generate an SSH key pair using `ssh-keygen -t rsa -b 4096 -C "your-github-email"`.

2. Start the SSH agent by running `eval "$(ssh-agent -s)"`.
3. Check or create a configuration file in the `.ssh` directory by running the following commands:
```
ls ~/.ssh
touch ~/.ssh/config
open ~/.ssh/config
```
4. Add the following configuration, replacing `githubusername`:
```
Host github.com-githubusername
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa
```
5. Add the private key to the SSH agent `ssh-add -K ~/.ssh/id_rsa`.
6. Copy the public key and add it to your GitHub account `pbcopy < ~/.ssh/id_rsa.pub`.
7. Verify the SSH connection by running `ssh -T git@github.com`.

One more step you would to consider to complete for integrating AWS workflows is to install AWS CLI. I recommend to do it via Homebrew, by running the following command: `brew install awscli`. Verify the installation by running `aws --version`.

This guide should serve you a foundation for understanding and implementing version control, Git, and GitHub workflows effectively. Getting to know these basics will give you a good start in your cloud engineering journey and enhance collaboration while working on the projects. 



