# Downloading (Source Control)

This class uses GitHub for its source control needs, which uses `git`. See more information at the [git docs](https://git-scm.com/docs).
We will use git to download and maintain version control of your project as you develop. This is to allow for teamwork and control of changes happening to the code base.

## Git: Branches
A branch is a variant of the main code, which may contain a fix, change, or new feature. This allows for multiple people to be working on the code base at once. There is one core branch, which is used for building releases and as the official version for new branches, which is called `main`. You should never commit to `main` directly, but rather make a pull request to have your branch merged into `main`.

## Git: Installing
If you do not already have git (i.e. `git` is invalid in terminal), you can install it by running:
```sh
$ sudo apt update
$ sudo apt install git
```
## Git: Configuring User (SSH) Authorization
To authorize our local machine to be able to make changes to our repo with our GitHub credentials, we will utilize a public-private SSH key pair.

### Generate an SSH Key
To generate an SSH key, run the following command:
```sh
$ ssh-keygen -t rsa -b 4096
```
Press enter when prompted.

### Add the SSH Key to GitHub
Now that you've generated a new SSH key pair, you need to add that SSH key to GitHub to authorize its use. 
1. Go to your Profile -> Settings
2. SSH and GPG keys
3. New SSH key
4. Name it your computer's name and paste in the key from `~/.ssh/id_rsa.pub` (which is where it output the generated key)

## Git: Clone the Repository
Now that your machine is authorized to use your GitHub user to commit and use the repo, we need to actually download the repo onto the filesytem. This can be done by using the clone command.
```sh
$ git clone git@github.com:CSU-CS-314-Fall-2021/t01.git
```

Be sure to follow the SSH format, rather than an `HTTP://` or `HTTPS://` git clone URL, which will result in your git not properly using your configured SSH authorization. This means that it will prompt you each time for a username and password, which our SSH configuration avoids.
