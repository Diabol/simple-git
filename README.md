# simple-git
A tutorial to introduce basic level git skills

## Initial configuration

Git must be configured to know who you are. This is done using the ```git config``` command.

```$ git config --global user.name "Your Name"```

```$ git config --global user.email "your.name@your.company"```

## Cloning repositories

Let's clone, grab a complete copy of, a git repository

TODO: Replace with actual example repository
```git clone ssh://git@github.com:Diabol/simple-git.git```

### Passwordless authentication (and yes, it really is secure!)

#### Generating SSH keys

```$ ssh-keygen -b 4096 -C "your.name@your.company"```

#### Install your public SSH key to your central git server

Depends on tool actually used, fairly similar for most. (Somewhere in your account preferences)

#### Public/Private parts of an SSH Key

The private part of the SSH key is _your_ secret. Protect at all times!

The public key is used to identify you. Share it!

### Clone again!

Now that you have a working SSH key git clone should succeed. Please try it!

## Adding things to git

1. Check current status in repository
    
    ```$ git status```

2. Create a directory

    ```$ mkdir your.name```

    ```$ cd your.name```

    ```$ git status```

3. Create a new file

    ```$ touch hello.txt```
 
    ```$ git status```

4. Add file to git

    ```$ git add hello.txt```
    
    ```$ git status```

## Committing things to git

```$ git commit -m "My first commit"```

```$ git status```

## Changing things in git

1. Editing and diffing changes

   ```$ echo "Hello, world!" > hello.txt```
   
   ```$ git status```
   
   ```$ git diff```

2. Adding and diffing changes

   ```$ git add hello.txt```
   
   ```$ git status```
   
   ```$ git diff```
   
   ```$ git diff --staged```

3. Commit it!

```$ git commit -m "Hello world example"```

## Viewing commit history

1. Viewing all commits

    ```$ git log```

2. Viewing details for a specific commit

    ```$ git show <commit-hash>```

3. Referencing historical commits

    ```$ git show HEAD~1```

## 