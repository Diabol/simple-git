# simple-git
A tutorial to introduce basic level git skills

## Initial configuration

Git must be configured to know who you are. This is done using the `git config` command.

```
$ git config --global user.name "Your Name"
$ git config --global user.email "your.name@your.company"
```

## Cloning repositories

Let's clone, grab a complete copy of, a git repository

TODO: Replace with actual example repository
`git clone ssh://git@github.com:Diabol/simple-git.git`

### Passwordless authentication (and yes, it really is secure!)

#### Generating SSH keys

```
$ ssh-keygen -b 4096 -C "your.name@your.company"
```

#### Install your public SSH key to your central git server

Depends on tool actually used, fairly similar for most. (Somewhere in your account preferences)

#### Public/Private parts of an SSH Key

The private part of the SSH key is _your_ secret. Protect at all times!

The public key is used to identify you. Share it!

### Clone again!

Now that you have a working SSH key git clone should succeed. Please try it!

## Adding things to git

1. Check current status in repository

    `$ git status`

    When you don't have any changes made git will tell you that like this:

    ```
    On branch master
    Your branch is up-to-date with 'origin/master'.
    nothing to commit, working tree clean
    ```

2. Create a directory

    ```
    $ mkdir your.name
    $ cd your.name
    $ git status
    ```

    Git doesn't care about directories unless there's file content in them. There fore git will still respond with an _up-to-date_ message as before, like this:

    ```
    On branch master
    Your branch is up-to-date with 'origin/master'.
    nothing to commit, working tree clean
    ```

3. Create a new file

    ```
    $ touch hello.txt
    $ git status
    ```

    Now when we have a file which we can track git will respond differently when we ask for _status_, like this:

    ```
    On branch master
    Your branch is up-to-date with 'origin/master'.
    Untracked files:
    (use "git add <file>..." to include in what will be committed)

	  ./

    nothing added to commit but untracked files present (use "git add" to track)
    ```

    If you have [colours](https://git-scm.com/book/gr/v2/Customizing-Git-Git-Configuration) enabled you will see that the untracked file (or the directory containing the untracked file) is red.

    Depending on the git installation, an alias for showing untracked files might be activated, making the status message show the actual file that could be tracked instead of the directory containing that file. Like this:

    ```
    $ git status -uall
    On branch master
    Your branch is up-to-date with 'origin/master'.
    Untracked files:
      (use "git add <file>..." to include in what will be committed)

	     hello.txt

    nothing added to commit but untracked files present (use "git add" to track)
    $
    ```

4. Add file to git

   Before having a file tracked we need to stage it for commit. This is done with the _add_ command.

   It is considered good praxis to group changes that are related to one and other to a single commit, having a traceable message describing the change that is made.

   The staging part is really handy when you have several  changes made to different files but want to keep track of them by different change messages.

   ```
   $ git add hello.txt
   $ git status
   ```

   Now the status message indicates that we have a change ready for commit, like this:

   ```
   On branch master
   Your branch is up-to-date with 'origin/master'.
   Changes to be committed:
   (use "git reset HEAD <file>..." to unstage)

	   new file:   hello.txt

   ```

   Also, if you have colours enabled, you will see that the files containing the changes now are green.

## Committing things to git

```
$ git commit -m "Added hello file"
$ git status
```

## Changing things in git

1. Editing and diffing changes

   ```
   $ echo "Hello, world!" > hello.txt
   $ git status
   $ git diff
   ```

2. Adding and diffing changes

   ```
   $ git add hello.txt
   $ git status
   $ git diff
   $ git diff --staged
   ```

3. Commit it!

   `$ git commit -m "Hello world example"`

## Different undo actions

1. Undo edits

   ```
   $ echo "Undo this edit" > hello.txt
   $ git diff
   $ git checkout hello.txt
   $ git diff
   ```

2. Undo staged edits

   ```
   $ echo "Undo staged edit" > hello.txt
   $ git add hello.txt
   $ git diff --staged
   $ git reset hello.txt
   $ git status
   $ git checkout hello.txt
   ```

## Viewing commit history

1. Viewing all commits

    ```$ git log```

2. Viewing details for a specific commit

    ```$ git show <commit-hash>```

3. Referencing historical commits

    ```$ git show HEAD~1```

## Branches in git

Everything is a branch!
