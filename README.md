# git-backup
A simple tool to backup (commit &amp; push to a branch) your current work-in-progress git workspace

## Use case
This tool is useful for those who want to push the current progress to a remote *work-in-progress* branch for backup reasons. It automates this job and avoids code not being backed up due to programmer's lazyness.

## Usage
Or your current workspace, just type:

```sh
$ git-backup
```

This will create a commit with all modified files and push to a remote branch in the format `backup-username`.

### Untracked content
If there are any untracked files, your default `$EDITOR` will open listing all untracked files where you'll be able to delete those you don't want to backup.

### Using a different remote
By default `git-backup` use the `origin` remote but that can be changed by passing another remote as argument.

Say you have a private fork of the project on bitbucket, you just pass your remote name as argument:

```sh
$ git-backup bitbucket
```

Your progress you'll be backed up at `bitbucket/backup-username`

## Installing
Clone this repository to any location of your system:

```sh
$ git clone https://github.com/omailson/git-backup.git ~/.git-backup
```

Add `git-backup` to your path (add the following line to your .bashrc)

```bash
export PATH=$HOME/.git-backup/bin:$PATH
```

## Use as a git alias

How about using `git backup` instead of `git-backup`? Just add a git alias:

```sh
$ git config --global alias.backup '!git-backup'
```

Now you can run `git-backup` as if it was yet another git command

```sh
$ git backup
```
