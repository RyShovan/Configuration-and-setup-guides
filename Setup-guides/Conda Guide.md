# Conda Guide


## Conda Basics

Verify conda is installed or check version number:
`conda info`

Update conda to the current version:
`conda update conda`

Install a package included in Anaconda:
`conda install PACKAGENAME`

Update any installed program
`conda update PACKAGENAME`

To **update python version** of current virtual environment in conda:
`conda update python`

## Using Environment

Create a new environment named py35, install Python 3.5
`conda create --name py35 python=3.5`
or
`conda create -n py35 python=3.5`

Activate the new environment to use it
`conda activate py35`
or
`source activate py35`

If conda is not added to your path in .bashrc or .zshrc, then activate conda by,
`source ~/miniconda3/bin/activate` and then you can activate conda virtual environment by `conda activate virtual-env-name`

Get a list of all my environments, active environment is shown with *
`conda env list`
or
`conda info --envs`

Make exact copy of an environment
`conda create --clone py35 --name py35-2`

List all packages and versions installed in active environment
`conda list`

List the history of each change to the current environment
`conda list --revisions`

Restore environment to a previous revision
`conda install --revision 2`

Save environment to a text file
`conda list --explicit > bio-env.txt`

Delete an environment and everything in it
`conda env remove --name virtual-env-name`

Deactivate the current environment
`source deactivate virtual-env-name`
or
`conda deactivate virtual-env-name`

Create environment from a text file
`conda env create --file bio-env.txt`


## Finding conda packages

Use conda to search for a package
`conda search PACKAGENAME`

If you want to see which **python versions are ready to be installed** via conda:
`conda search python`

See list of all packages in Anaconda
https://docs.anaconda.com/anaconda/packages/pkg-docs



## Installing and updating packages

Install a new package (Jupyter Notebook) in the active environment
`conda install jupyter`

Run an installed package (Jupyter Notebook)
`jupyter-notebook`

Install a new package (toolz) in a different environment (bio-env)
`conda install --name bio-env toolz`

Update a package in the current environment
`conda update Jupyter`


Install a package directly from PyPI into the current active environment using pip or pip3
`pip install jupyter`
or
`pip3 install jupyter`

Remove one or more packages (jupyter, spyder) from a specific environment (bio-env)
`conda remove --name bio-env jupyter spyder`



## Managing multiple versions of Python

Install different version of Python in
a new environment named py34
`conda create --name py34 python=3.4`

Show the locations of all versions of Python that are currently in the path
NOTE: The first version of Python in the list will be executed.
Show version information for the current active Python
`which -a python`

## Run directly with a version of python without sourcing it

Run the run.py directly from the terminal with a specific version of python
`/home/user/miniconda3/envs/py36/bin/python3 run.py`
or
`/home/user/miniconda3/bin/python3 run.py`


## For Bash, Zsh and Fish Shell Configuration

For Bash or Zsh add this code block to .bashrc or .zshrc.

```
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/user/miniconda3/bin/conda' 'shell.zsh' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/user/miniconda3/etc/profile.d/conda.sh" ]; then
        . "/home/user/miniconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/user/miniconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```




For Fish Shell add this lines to your `~/.config/fish/config.fish` file.

```
# >>> conda initialize >>>
eval /home/user/miniconda3/bin/conda "shell.fish" "hook" $argv | source
# <<< conda initialize <<<
```

- **Just Don't Forget to replace `user` with your `username`.**


## Install Conda or Miniconda

I personally prefer miniconda over Conda. Install from [here](https://docs.conda.io/en/latest/miniconda.html "Miniconda").

Download *Miniconda3-latest-Linux-x86_64.sh* file and run `./Miniconda3-latest-Linux-x86_64.sh` in the terminal.