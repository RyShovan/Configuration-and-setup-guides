# Jupyter Notebook Guide



## Notebook commands

To install jupyter notebook
`pip install jupyter`

To jupyter notebook config file
`jupyter notebook --generate-config`

To see which kernels are listed in jupyter notebook
`jupyter kernelspec list`

To remove a kernel
`jupyter kernelspec remove kernel-name`

To generate password for jupyter notebook
`jupyter notebook password`


To start jupyter notebook in a specific diretory
`jupyter notebook --notebook-dir /user/Jupyter/`
>Replace user with your username.



## Notebook Config file

To open jupyter notebook other than default browser
`c.NotebookApp.browser = 'browser-name-and-option %s'`

Top open jupyter notebook in only localhost
`c.NotebookApp.ip = 'localhost'`

To open jupyter notebook in all devices
`c.NotebookApp.ip = '*'`
> Note: You have to activate jupyter password facility to properly use this feature.



## Shortcuts in Notebook

You can use custom shortcuts for jupyter notebook.

Personally I use these shortcuts.

```
"e,e,e": "jupyter-notebook:restart-kernel-and-clear-output",
"ctrl-shift-down": "jupyter-notebook:move-cell-down",
"ctrl-shift-up": "jupyter-notebook:move-cell-up"
```

## Others

To check python version inside jupyter notebook run this two commands.

```
import sys
print(sys.version)
```

To check execution time of any code use
`%%time` above the code.
