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
