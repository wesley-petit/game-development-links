# How to configure GIT for Game Development ?

## Introduction
GIT was made for source code versioning and not large binary files handling. Even with [GIT LFS support](https://git-lfs.com/), it's often lead to a tricky merge between two files that are not human friendly.

But game development mainly consists of large binary files (models, scenes...), so why use it?

Because it's generally one of the first versioning method learned by a programmer, so there is no need to learn, install and configure another versioning software.
And, in my case, I often found GIT skills requirements in job offers.

Download GIT depending on your OS version [here](https://git-scm.com/downloads).

## Configuration
### Install GIT LFS on a repository
If you want to migrate an existant repository to GIT LFS, follow [these instructions](https://notiz.dev/blog/migrate-git-repo-to-git-lfs).

1. Open a terminal.

2. Go to your repository directory.

3. Install GIT LFS in your repository.
```bash
git lfs install
```

5. Download a .gitattributes corresponding of your game engines (e.g. [Unreal Engine](https://gist.github.com/wesley-petit/0263a4ade975ce0d30aaccd153e40f1a)).

6. Add the .gitattributes at the root of your repository and push it to support LFS.


### Configure End Line standard
Here some links [explaining the subject](https://www.aleksandrhovhannisyan.com/blog/crlf-vs-lf-normalizing-line-endings-in-git/#line-endings-in-git) and a description of [all command use in this tutorial.](https://adaptivepatchwork.com/2012/03/01/mind-the-end-of-your-line/).

1. Open a terminal.

2. Type the command.
```bash
git config --global core.safecrlf true
```

3. You are good to go.

You can customize your gitattributes to follow a strict end line regulations, GitHub has a small ["how to"](https://docs.github.com/fr/get-started/getting-started-with-git/configuring-git-to-handle-line-endings?platform=windows#per-repository-settings) on their websites.


### Change pull behavior to rebase
I personnaly change the pull behavior with rebase to avoid not needed merge with local commits. [Here](https://stackoverflow.com/questions/13846300/how-to-make-git-pull-use-rebase-by-default-for-all-my-repositories) is a link to all the options available.

1. Open a terminal.

2. Type The command.
```bash
git config --global pull.rebase true
```

3. Rebase is the default option when you pull any repository of your computer.
