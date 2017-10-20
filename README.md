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
