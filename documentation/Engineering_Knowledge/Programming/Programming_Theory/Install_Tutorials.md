## Install anaconda :



## Import yml environment :



## Install python connector, and workbench for your os :

#### 	if issues with python connector :

Format the connect_string this way :

```python
connect string = 'mysql+mysqlconnector://user:password@mysql_server/database?use_pure=True'
```

​		**?use_pure=True** allow you to bypass the C implemented libraries to acess the mysql server.

## Jupyter lab extensions :

​	<u>To run jupyter lab integrated widgets :</u>

```shell
pip install ipywidgets
```

​	install and activate in conda env with :

```shell
jupyter labextension install @jupyter-widgets/jupyterlab-manager
jupyter nbextension enable --py widgetsnbextension
```



## Install MKdocs :

To run automatically a batch file at startup :

Open Run ( search run ou executer )

type shell:startup or "C:\Users\Timothe\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup" in the explorer



## Trouble Shoot :

1. ##### [Cannot install new packages :](https://github.com/conda/conda/issues/9003)

   If conda cause issues with "openssl_sk_new_reserve could not be located" and cannot install new packages :  

   copy libssl-1_1-x64 dlls from 

   ```
   C:/Users/user/Anaconda3/DLLS
   ```

    to 

   ```
   C:/Users/user/Anaconda3/Library/bin
   ```

   (overwrite, probably dates are different and are causing the issue)

2. ##### Calling several commands in one .bat file

   use call before a command, if not, the command will be executed and the shell closed once done, even if there is still code in the file. ( ex conda activate, without call : exits after env has been activated) 