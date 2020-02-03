# Git

## Basics

```text
git --version
```

```text
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

```text
git init
```

```text
git status
```

```text
git add file.js
git add .
```

```text
git commit -m "Commit message"
```

```text
git log
git log --oneline
```

```text
git checkout <commit-hash>
git checkout master
```

```text
git branch <new-branch-name>
git checkout <branch-name>

// or
git checkout -b <new-branch-name>
```

#### 2 Branches zusammenführen

* Zuerst in den Ziel Branch wechseln

```text
git merge <branch-name>
```

#### Branch löschen

```text
git -d <branch-name>
```

{% embed url="https://www.notion.so/Introduction-to-Git-ac396a0697704709a12b6a0e545db049" %}

### Three Sections of a Git Project <a id="understand-the-three-sections-of-a-git-project"></a>

The **Git directory** \(located in `YOUR-PROJECT-PATH/.git/`\) is where Git stores everything it needs to accurately track the project. This includes metadata and an object database which includes compressed versions of the project files.

The **working directory** is where a user makes local changes to a project. The working directory pulls the project's files from the Git directory's object database and places them on the user's local machine.

Note: **Directory** is also known as **Repository** or short form repo. The repo on the user's local machine is called "Local repo" while the repo on git server is called "Remote repo".

The **staging area** is a file \(also called the "index", "stage", or "cache"\) that stores information about what will go into your next commit. A commit is when you tell Git to save these staged changes. Git takes a snapshot of the files as they are and permanently stores that snapshot in the Git directory.

![](../../.gitbook/assets/1_9qx9f9mgswkfcmgtor9bpw.png)



