# Github guide for Linux

## Push the repository from local directory

- Create a repository in github.
- Don't select `create README.md and .gitignore files`.
- Now go to the root directory of your project and start the terminal in that directory.
- Now run the followoing commands given below-
- `git init`
- `git add .`
- `git commit -m "first commit"`
- `git branch -M master`

To connect git with https use this command.
- `git remote add origin https://github.com/RyShovan/ShareCode.git`

To connect git with ssh use this command.
- `git remote add origin git@github.com:RyShovan/ShareCode.git`

Put your `username` and `repository name`.

At last push the repository to github server.
- `git push -u origin master`


## SSH guide for git

**This guide is for bash and zsh shell.**

### Legacy method:
Create a ssh key:
`ssh-keygen -t rsa -b 4096 -C "put-your-email-id"`

Check the keys:
`ls -al ~/.ssh`

Copy the public key to clipboard with *xclip*. You may have to install *xclip*.
`xclip -sel clip < ~/.ssh/id_rsa.pub`

**If you don't want to use xclip**, just run `gedit ~/.ssh/id_rsa.pub` and then copy the key.

Add this public key to github server. Open https://github.com/settings/keys and paste the key there.

Now run `git remote set-url origin git@github.com:RyShovan/ShareCode.git`

Now you will be able to push repository with ssh.

### New Method (More secured)
- run `ssh-keygen -t ed25519 -C "your_email@example.com"`
- When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location.

> Enter passphrase (empty for no passphrase): [Type a passphrase]

> Enter same passphrase again: [Type passphrase again]

- Start the ssh-agent in the background.

> $ eval "$(ssh-agent -s)"

- you will get `Agent pid 59566`
- If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

> ssh-add ~/.ssh/id_ed25519

- Add the SSH public key to your account on GitHub. For more information, see ["Adding a new SSH key to your GitHub account"](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).

- Copy the SSH public key to your clipboard.

> $ cat ~/.ssh/id_ed25519.pub

- Then select and copy the contents of the id_ed25519.pub file displayed in the terminal to your clipboard.
- For testing your SSH connection with github run: `ssh -T git@github.com`
- You may see a warning like this:

> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
ED25519 key fingerprint is SHA256:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])?

- type `yes` and hit enter.
- you will get `Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Hi User! You've successfully authenticated, but GitHub does not provide shell access.`
- that's it. You are done here. Now it should work fine.



## Changing remote-url protocol

Check the remote url protocol
`git remote -v`

To use SSH protocol: 
`git remote set-url origin git@github.com:RyShovan/ShareCode.git`

To use HTTPS protocol: 
`git remote set-url origin https://github.com/RyShovan/ShareCode.git`


## Other Commands

#### Clear cache of local git repository

You can clean git cache of your local directory by running-
`git rm -r --cached .`

This command is helpful if you added some files to .gitignore file which were already present in the git cache.
Run the command and then commit.


#### Undo a commit and redo

`git commit -m "Some mistake"`
`git reset HEAD~1`
or
`git reset --hard HEAD~1`
> << edit files as necessary >>

`git add .`
`git commit -c ORIG_HEAD`

Please follow this [**link**](https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git "Undo a commit in git") for better understanding.