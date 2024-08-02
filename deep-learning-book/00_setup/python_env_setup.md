# First Time Coding in Python?

This section will help you figure out how to run scripts using Python. As you may be aware of by now, Python is an _interpreted_ language. This means that you don't need to compile code before running it, but it comes with a downside - you need to have an environment that meets all of the requirements of your script before you can run the code.

> This guide is based on the one in Tom Beucler's [course](https://tbeucler.github.io/2023_MLEES_Published_Book).

## What do I mean by environment?
In this context, environment refers to the base Python interpreter, which translates the code you write in Python to commands computers can understand and execute, plus any other required libraries and modules (i.e., code written by others that has conveniently been shared with you and which generally makes coding more straightforward). These libraries allow you to, e.g., efficiently carry out numerical operations (Numpy), effectively handle data structure and data analysis tasks (Pandas), and even implement state of the art machine learning solutions (SciKit Learn, Tensorflow, PyTorch).

Today, we'll be looking at three options for running Python code:
1. Google Colaboratory (oftened shortened to Colab)
> Colab is a service run by Google, and gives you (limited) access to their CPUs, GPUs, and even TPUs! Colab is based on Jupyter Notebooks, and is meant to allow you to write and execute Python code from within your browser free of charge. It has many popular machine learning libraries installed, and has APIs to interact with Google services (e.g., Drive). Colab, however, requires you to log in with a Google account, which you may understandably may not have or want to have.  
>> *Plusses*: Free of Charge, Integrates with Google services, Integrates with GitHub, *Requires no setup on your end for most tasks*    
>> *Minuses*: Your code will be stored and run on Google servers, Requires the use of a Google Account, Limited Resources, Limited to Interactive Scripts  
2. Binder
> Like Colab, Binder is an online platform that allows you to write and execute Python code from your browser. Unlike Colab, The Binder Project is an *open-source* initiative that allows the creation of custom computing environments for interactive and reproducible data science and scientific computing. With it, you can turn GitHub repositories containing Jupyter notebooks or other data science code into executable environments that others can launch and interact with online, without the need to install anything locally.  
>> *Plusses*: Free of charge, Open Source, Integrates with GitHub, *Requires no setup on your end for most tasks*, Support for Complex Environments (including Docker)  
>> *Minuses*: Limited Resources, Setup complexity for new users, Building time can be long, Your code will be stored and run on external servers, *you cannot save changes made to the files in the server; you have to download the files*
3. Conda (using Miniconda)  
> Conda is a package manager that allows you to create and manage environments for Python and other languages. It is a very powerful tool, and is the recommended way to manage your Python environments. Conda is available in two versions: Anaconda and Miniconda. Anaconda is a full-fledged distribution of Python, and comes with many pre-installed packages. Miniconda, on the other hand, is a minimal version of Anaconda, and only comes with the bare minimum to get you started. We will be using Miniconda today, as it is much lighter and easier to install. Additionally, we can use Conda with a variety of IDEs (Integrated Development Environments), which allow us to write and execute Python code from our computers.  
>> *Plusses*: Free of charge, Open Source and Cross-Platform, *Allows you to create and manage your own environments*, *handles library dependency compatibility for your environments*, Your code will be stored and run on the computer where Conda is installed (*You can run code offline*)  
>> *Minuses*: Setup complexity for new users, *Requires you to install software on your computer*, *Requires you to manage your environments*  

Let's go over how to use each of these options.


## Google Colaboratory 🥼
To use Colab, you need to have a Google account. If you don't have one, you can create one [here](https://accounts.google.com/signup/v2/webcreateaccount?flowName=GlifWebSignIn&flowEntry=SignUp). Once you have an account, you can access Colab [here](https://colab.research.google.com/). You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Colab_Screens/Opening_Colab.png?raw=true' width=50%>

From this page, you can open up a new notebook by clicking on 'New Notebook' or by clicking on 'File' and then 'New Notebook'. You should then see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Colab_Screens/Colab_New_Notebook.png?raw=true' width=50%>

You can now write and execute Python code in this notebook. To execute a cell, you can either click on the 'play' button to the left of the cell, or you can press 'Shift+Enter' on your keyboard. Try it out by copying the following text into a cell and executing the code:  
```python
print('Here is the list of all the packages installed in this environment:')
!pip list
```

This is nice, but what we're most interested in today is to be able to run tutorials hosted on GitHub. There are a couple of ways to do this,
1. If the jupyter notebook hosted on GitHub and was uploaded via the Colab interface, you can simply click on the "Open in Colab" button at the top of the page.  
><img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Colab_Screens/open_in_colab.png?raw=true' width=10%> <br>
>This will open the notebook in Colab, and you can then execute the code as you would normally. You can find an example of this [here](https://github.com/msgomez06/ML_pedagogical_materials/blob/main/Labs/S2_1_Classification.ipynb). This notebook is part of a series materials developed for a course on Machine Learning given at UNIL, and is hosted on GitHub.  

2. If the notebook is hosted on GitHub, but was not uploaded via the Colab interface, you can use the URL pattern in order to open it on Colab.  
As an example, we'll use the notebooks developed by Jesper Dramsch for the EuroSciPy 2022 tutorial [Machine Learning for Science Reproducibility](https://github.com/JesperDramsch/ml-for-science-reproducibility-tutorial/tree/main). Though the materials have been prepared for opening with Colab and Binder (as evidenced by the _open on_ widgets on the main Readme.md), let's pretend they weren't and [view the first notebook on GitHub](https://github.com/JesperDramsch/ml-for-science-reproducibility-tutorial/blob/main/book/notebooks/0-basic-data-prep-and-model.ipynb). When viewing the hosted notebook in your browser, you should see that the URL is  
`https://github.com/JesperDramsch/ml-for-science-reproducibility-tutorial/blob/main/book/notebooks/0-basic-data-prep-and-model.ipynb`.  
To open this notebook in Colab, you need to replace `github.com` with `colab.research.google.com/github`.  
The resulting URL should be  
`https://colab.research.google.com/github/JesperDramsch/ml-for-science-reproducibility-tutorial/blob/main/book/notebooks/0-basic-data-prep-and-model.ipynb`  
If you open this URL, you should see the notebook open in Colab, and you can execute the code as you would normally.
Try it out by yourself with the following notebook:
`https://github.com/JesperDramsch/ml-for-science-reproducibility-tutorial/blob/main/book/notebooks/1-model-evaluation.ipynb`

3. You can also use Colab's `Open Notebook` command from the file menu, which will allow you to search through GitHub repositories by user, as shown in the screenshot below.  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Colab_Screens/open_from_github.png?raw=true' width=50%> <br>



## Binder 📒
Binder is a bit more complicated to use than Colab, but it is also more powerful. We won't go into the details of how to create a Binder environment, but we will go over how to use one.

Let's start by opening the Binder environment for the EuroSciPy 2022 tutorial [Machine Learning for Science Reproducibility](https://mybinder.org/v2/gh/JesperDramsch/ml-for-science-reproducibility-tutorial/HEAD). You should see a screen like this:  
<img src='Binder_screens\binder_loading.png?raw=true' width=50%> <br>
This screen indicates that Binder is building the environment for you.  
_This can take a while, so please be patient._  
Once the environment is built, you should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Binder_screens\binder_jplab.png?raw=true' width=50%> <br>
Unlike with Colab, Binder launches a full instance of JupyterLab and not just the notebook interface. This allows you to open and edit multiple notebooks at the same time, and even to open other files (e.g., images, text files, etc.)! You can use the file explorer on the left plane to browse the contents of the repository, and you can open a notebook by double-clicking on it. Here is the first notebook in the repository, `0-basic-data-prep-and-model.ipynb`:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Binder_screens\binder_notebook.png?raw=true' width=50%> <br>
Note that if you want to run this notebook, at the time of writing, you should change the line  
`DATA_FOLDER = Path("..") / "data"`  
to  
`DATA_FOLDER = Path("../..") / "data"`

<br><br>

## Conda (using Miniconda) 🐍

Conda is a much more flexible solution for running Python code, but it requires you to install software on your computer. In this tutorial, we'll go over how to install Miniconda on Windows and Linux (apologies to those on OSX - I don't have access to a Mac, so I can't provide the same level of instructions for you - it should however be quite similar).

Before we get into the installation, let's go over some basic terminology:

### Terminology
- **Package**: A package is a collection of code that can be installed and used in Python. Packages can be installed from a variety of sources, including the Python Package Index (PyPI), Anaconda Cloud, and Conda-Forge. Packages can be installed using the `conda` command, or using `pip` (the Python Package Installer). We will be relying on `conda`, as it ensures that all of the dependencies of a package are installed as well (and checks for conflicts between packages)
- **Virtual Environment**: Like we mentioned before, an environment is a collection of packages that are installed in a specific location - Python environments contain all of the software needed to interpret code and run Python Scripts. Virtual environments are useful because they allow you to have different versions of packages installed in different environments, and they allow you to easily share your environment with others. Environments can be created using the `conda` command, or using `pipenv` (the Python Package Installer Environment).
- **Channel**: A channel is a source for packages. The default channel is the Anaconda channel, which contains packages that have been tested by the Anaconda team. Other channels include Conda-Forge, which contains packages that have been tested by the Conda-Forge team, and PyPI, which contains packages that have been uploaded by the community. Channels can be specified when installing packages using the `conda` command.

### Installing Miniconda
To install Miniconda, you need to download the installer for your operating system from [here](https://docs.conda.io/en/latest/miniconda.html). Once you have downloaded the installer, you can run it to install Miniconda. To jump to the instructions for Linux, click [here](#linux-🐧). To jump to the instructions for Windows. The ones for Windows are right below.
<br>

#### Windows 🗔
Once you have downloaded the installer, run it and follow the instructions with the default settings. You should now have a program called `Anaconda Prompt` and `Anaconda Powershell Primpt` installed on your computer. These programs allows you to run commands in a terminal with the correct environment activated - let's start by opening 'Anaconda Powershell Prompt'. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/anaconda_powershell_prompt.png?raw=true' width=50%> <br>
Notice the `(base)` at the beginning of the line - this indicates that the `base` environment is currently active. Let's create a new environment called `test_env` by running the following command:
```bash
conda create -n test_env
```
You should be asked to confirm the installation of the new environment by typing `y` and pressing `Enter`. Once the environment is created, you should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/create_env.png?raw=true' width=50%> <br>
If you run the `conda env list` command, you should now see both the `base` and `test_env` environments listed. Let's go ahead and activate the `test_env` environment by running the following command:
```bash
conda activate test_env
```
If you run `conda list`, you'll get a list of the packages installed on the virtual environment. For the moment, that list is empty! (We did, after all, just create a blank virtual environment)
Let's go ahead and install ipython, short for interactive python, and which will let us run Python code interactively. To do this, we'll run the following command:
```bash
conda install ipython
```
Conda will generate a list of packages that will be installed, and will ask you to confirm the installation by typing `y` and pressing `Enter`. Once the installation is complete, you should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/ipython_install.png?raw=true' width=50%> <br>
Now type in `ipython` and press `Enter`. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/ipython.png?raw=true' width=50%> <br>
Try running a small program that prints out the numbers from 0 to 9:
```python	
[print(number) for number in range(10)]
```
You should see the following:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/ipython_example.png?raw=true' width=50%> <br>
Once you're done with ipython, simply type `exit()` and press `Enter` to exit the program.
Let's now install a few commonly used packages. To do this, we'll use a different channel than the default one. Simply add `-c conda-forge` as an option to the install command, as shown below:  
```bash
conda install -c conda-forge numpy pandas matplotlib
```
Congratulations, you have a working Python environment! We'll go over how to install IDEs in the next section; just skip over the Linux section for now.

<br><br>

#### Linux 🐧
After you've downloaded the installer, open a terminal and navigate to the directory where you downloaded the installer. Assuming you used Firefox, the default command to take you to the directory where the installer is located is:
```bash
cd ~/Downloads
```
Once you're in the correct directory, run the following command to make the installer executable:
```bash
chmod +x Miniconda3-latest-Linux-x86_64.sh
```
Then, run the installer:
```bash
bash Miniconda3-latest-Linux-x86_64.sh
```
You will be prompted to accept the license agreement. Press `Space` to scroll through the license agreement, and then type `yes` and press `Enter` to accept the license agreement. You will then be asked to confirm the installation location. Press `Enter` to accept the default location. You will then be asked if you want to initialize Miniconda3 by running `conda init`. Type `yes` and press `Enter` to accept. Restart your terminal, and you should now see `(base)` next to the prompt. This indicates that the `base` environment is currently active:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/linux_conda_init.png?raw=true' width=50%> <br>
Let's create a new environment called `test_env` by running the following command:
```bash
conda create -n test_env
```
You should be asked to confirm the installation of the new environment by typing `y` and pressing `Enter`. Once the environment is created, you should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/linux_create_env.png?raw=true' width=50%> <br>
If you run the `conda env list` command, you should now see both the `base` and `test_env` environments listed. Let's go ahead and activate the `test_env` environment by running the following command:
```bash
conda activate test_env
```
If you run `conda list`, you'll get a list of the packages installed on the virtual environment. For the moment, that list is empty! (We did, after all, just create a blank virtual environment)
Let's go ahead and install ipython, short for interactive python, and which will let us run Python code interactively. To do this, we'll run the following command:
```bash
conda install ipython
```
Conda will generate a list of packages that will be installed, and will ask you to confirm the installation by typing `y` and pressing `Enter`. Once the installation is complete, you should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/linux_ipython_install.png?raw=true' width=50%> <br>
Now type in `ipython` and press `Enter`. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/linux_ipython.png?raw=true' width=50%> <br>
Try running a small program that prints out the numbers from 0 to 9:
```python	
[print(number) for number in range(10)]
```
You should see the following:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/linux_ipython_example.png?raw=true' width=50%> <br>
Once you're done with ipython, simply type `exit()` and press `Enter` to exit the program.
Let's now install a few commonly used packages. To do this, we'll use a different channel than the default one. Simply add `-c conda-forge` as an option to the install command, as shown below:  
```bash
conda install -c conda-forge numpy pandas matplotlib
```
Congratulations, you have a working Python environment! We'll go over how to install IDEs in the next section.  
<br>


### Integrated Development Environments (IDEs)

IDEs are software that provide you with tools for writing code. While it _is_ true that you could write your programs in any text editor, you'll quickly run into issues - did you spell everything correctly? What arguments did `my_function` take again? What part of your code caused your script to fail? What is the current value of `my_variable`? IDEs can help answer these and many other questions.

Today, we'll be looking at three IDEs: Jupyter, Spyder, and Visual Studio Code (VScode for short). Jupyter is a web-based IDE that allows you to write and execute code in a web browser. Spyder is a desktop IDE that allows you to write and execute code in a single window. VScode is a desktop IDE that allows you to write and execute code in a single window, and which also provides you with a variety of tools for debugging and managing your code (including plugins for GitHub Copilot - an AI assistant that is free for students - at the time of writing, at least).
<br><br>

#### Jupyter Notebook 📓
We'll be using Jupyter Notebook for this tutorial, but there is also a JupyterLab interface that is more similar to Spyder and VScode. To install Jupyter, simply run the following command:
```bash
conda install -c conda-forge jupyter
```

*THATS IT!*  
You now have a working Python environment with Jupyter installed! To launch Jupyter, simply run the following command:
```bash
jupyter notebook
```
You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/jupyter.png?raw=true' width=50%> <br>
You can now browse to wherever you have your notebooks stored and open them. You can also create new notebooks by clicking on the `New` button on the top right corner of the screen.  
For the documentation on Jupyter Notebook, please refer to the [official documentation](https://jupyter-notebook.readthedocs.io/en/stable/).
<br><br>

#### Jupyter Lab 🧪
If you prefer the JupyterLab interface, you can install it by running the following command:
```bash
conda install -c conda-forge jupyterlab
```
You can then launch JupyterLab by running the following command:
```bash
jupyter lab
```
You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/jupyterlab.png?raw=true' width=50%> <br>
You can now browse to wherever you have your notebooks stored and open them. From the launcher, you can create a new Jupyter Notebook (and you can open additional launches by clicking on the + button at the top left corner of the screen).  
For the documentation on JupyterLab, please refer to the [official documentation](https://jupyterlab.readthedocs.io/en/stable/).
<br><br>

#### Spyder 🕷️
Spyder is a desktop IDE that allows you to write and execute code in a single window. (If you're curious, it stands for **S**cientific **Py**thon **De**velopment Envi**R**onment) To install Spyder, simply run the following command:
```bash
conda install -c conda-forge spyder
```
However, Spyder isn't configured to run Jupyter Notebooks by default, so we'll need to install a few additional packages. We will, after all, mostly work with Jupyter Notebooks. (Though you can do everything that is done in the course with scripts instead!) To install the required packages, run the following command:
```bash
conda install -c conda-forge spyder-notebook
```
Let's go ahead and start Spyder by running the following command:
```bash
spyder
```
You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/spyder.png?raw=true' width=50%> <br>
Spyder will open a temporary script file upon launching (`temp.py`). You'll notice at the bottom of the screen that there are two tabs: `Editor` and `Notebook`. Click on the `Notebook` tab to open the notebook interface. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/spyder-notebook.png?raw=true' width=50%> <br>
From this screen, you can create Jupyter Notebooks and open existing ones. Congratulations, you now have a working Python environment with Spyder installed! 😃
For the documentation on Spyder, please refer to the [official documentation](https://docs.spyder-ide.org/). For the documentation on Spyder-Notebook, please refer to the [official documentation](https://docs.spyder-ide.org/current/plugins/notebook.html).
<br><br>

#### Visual Studio Code (VScode) 🆚
VScode is a powerful, desktop IDE that allows you to write and execute code in a single window, and which also provides you with a variety of tools for debugging and managing your code (including plugins for GitHub Copilot - an AI assistant that is free for students - at the time of writing, at least). To install VScode, you'll have to download the installer from [the VScode website](https://code.visualstudio.com/download) and run it.

On windows, simply launch the installer. On Linux, navigate to the directory where you downloaded the installer and run the following command:
```bash
sudo dpkg -i code_1.60.2-1632313585_amd64.deb
```

Once you have VScode installed, launch it (either by clicking on the appropriate icon on Windows, or by running `code` in a terminal on Linux). You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/vscode_start.png?raw=true' width=50%> <br>

On the left, you'll see an icon that looks like a set of 3 blocks about to be joined by a fourth block. Click on it to open the extensions menu. Search for `Python` and install the first result. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/vscode_python.png?raw=true' width=50%> <br>

Go ahead and install the Jupyter extension on your own 😃.

Now that you have both of these installed, click on the `Explorer` icon on the left - it looks like two files stacked on top of each other. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/vscode_explorer.png?raw=true' width=50%> <br>

Click on the `Open Folder` button, and navigate to the folder where you have your notebooks stored. Select the folder and click on `Open`. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/vscode_folder.png?raw=true' width=50%> <br>

Let's go ahead and start a new notebook. Click on the `New File` button on the top left corner of the screen, and type in `test.ipynb`. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/new_jupyter_notebook.png?raw=true' width=50%> <br>

You should see 'select kernel' on the top right of the screen - click on it, choose Python Environment from the prompt, and select your virtual environment (e.g., test_env) from the list.  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Conda_screens/vscode_select_kernel.png?raw=true' width=50%> <br>
Try importing a library (you might be prompted by vscode to install some files required for the interactive running of jupyter notebooks - go ahead and accept this prompt).
Congratulations - you can now run Jupyter Notebooks from VScode! 😃

For the documentation on VScode, please refer to the [official documentation](https://code.visualstudio.com/docs).

<br><br>

### Using Git and GitHub

Git is a version control system that allows you to keep track of changes made to your code. GitHub is a service that allows you to store your code online, and which provides you with a variety of tools for collaborating with others. We won't go over how to use Git and GitHub in this tutorial, but we will go over how to install Git and how to clone a repository from GitHub. Additionally, we'll go over how to use the integrated Git tools in VScode. Finally, we'll discuss how to set up Github Copilot in VScode 🤖.

<br>

#### Installing Git on Windows
To install Git on Windows, you'll have to download the installer from [the Git website](https://git-scm.com/download/win) and run it - leave all of the default settings clicked. Once you have Git installed, you can open a terminal (e.g., the Powershell) and run the following command to check that it is installed correctly:
```bash
git --version
```
 <br>

#### Installing Git on Linux
To install Git on Linux, simply run the following commands:
```bash
sudo apt-get update
sudo apt install git
```
Answer `y` when prompted to confirm the installation. Once you have Git installed, you can open a terminal and run the following command to check that it is installed correctly:
```bash
git --version
```

<br><br>

#### Setting up your GirHub account
You don't need to create an account on GitHub to clone a repository, but you will need one if you want to push changes to a repository. To create an account, go to [the sign-up section of the GitHub website](https://github.com/signup). You'll be asked to enter your email (**REMEMBER TO USE YOUR ACADEMIC EMAIL IF YOU'RE PLANNING TO REQUEST STUDENT/TEACHER BENEFITS**) in the following screen:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/github_signup.png?raw=true' width=50%> <br>
Follow the prompts to create your account, and then verify your email address. You will then be asked for your preferences - if you're a student or teacher, you can apply for benefits associated with your status in this process. 
Once you've done that, let's go ahead and set up an SSH key. SSH keys are a way to identify trusted computers, without involving passwords. You will need to set this up in order to upload changes to GitHub - *password authentication is no longer supported* 🙅.

##### Setting up an SSH key on Linux
To set up an SSH key on Linux, you'll need to
1. Open a terminal and run the following command:  
```bash
ssh-keygen -t ed25519
```
You'll be asked to enter a file in which to save the key. Press `Enter` to accept the default location. You'll then be asked to enter a passphrase. You can either enter a passphrase or leave it blank. If you leave it blank, you'll be asked to confirm that you want to leave it blank - in our case we'll leave it blank (*NOTE THAT THIS IS LESS SECURE*). Once you've done that, you should see a screen like this:
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/linux_ssh_keygen.png?raw=true' width=50%> <br>

2. You can now view your SSH key by running the following command, after which you should copy the key to your clipboard.:
```bash
cat ~/.ssh/id_ed25519.pub
```

3. Now go to [your GitHub settings](https://github.com/settings/profile)

4. Click on `SSH and GPG keys` on the left side of the screen
5. Click on `New SSH key`
6. Give your key a title (e.g., `My SSH Key`)
7. Paste your key into the `Key` field
8. Click on `Add SSH key`

>Your SSH key should now appear in the list of SSH-keys on your GitHub settings, similar to the screenshot below:  
><img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/linux_github_ssh_key.png?raw=true' width=50%> <br>
<br><br>

##### Setting up an SSH key on Windows
To set up an SSH key on Windows, **after you've installed Git* you'll need to:
1. Open the start menu and search for `Powershell`. Right click on the icon and select `Run as administrator`.
2. Activate the ssh-agent by running the following command:
```bash
Get-Service ssh-agent | Set-Service -StartupType Automatic -PassThru | Start-Service
```
3. Run the following command to start the ssh-agent without restarting your computer:
```bash
start-ssh-agent.cmd
```
4. Run the following command to generate an SSH key:
```bash
ssh-keygen -t ed25519
```
>You'll be asked to enter a file in which to save the key. Press `Enter` to accept the default location. You'll then be asked to enter a passphrase. You can either enter a passphrase or leave it blank. If you leave it blank, you'll be asked to confirm that you want to leave it blank - in our case we'll leave it blank (*NOTE THAT THIS IS LESS SECURE*). Once you've done that, you should see a screen like this:  
><img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/windows_ssh_keygen.png?raw=true' width=50%> <br>
5. Navigate to the directory where you saved your SSH key (e.g., `C:\Users\username\.ssh\id_ed25519.pub`) and open the file in a text editor (e.g., Notepad). Copy the contents of the file to your clipboard. You should see something like this:
><img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/windows_ssh_key.png?raw=true' width=50%> <br>
6. Go to [your GitHub settings](https://github.com/settings/profile)
7. Click on `SSH and GPG keys` on the left side of the screen
8. Click on `New SSH key`
9. Give your key a title (e.g., `My SSH Windows Key`)
10. Paste your key into the `Key` field
11. Click on `Add SSH key`

> Your SSH key should now appear in the list of SSH-keys on your GitHub settings, similar to the screenshot below:  
><img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/windows_ssh_github.png?raw=true' width=50%> <br>

<br><br>

#### Cloning a GitHub repository
You should now be able to clone repositories from GitHub! Let's go ahead and clone the repository for the EuroSciPy 2022 tutorial [Machine Learning for Science Reproducibility](https://github.com/JesperDramsch/ml-for-science-reproducibility-tutorial/tree/main). Open the repository in your browser, and click on the `Code` button, then on the SSH tab. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/clone_code.png?raw=true' width=50%> <br>

Open a terminal and navigate to the directory where you want to clone the repository. Then, run the following command:
```bash
git clone git@github.com:JesperDramsch/ml-for-science-reproducibility-tutorial.git
```
If this is the first time you're cloning a repository, you'll be asked to confirm that you want to connect to the host. Type `yes` and press `Enter` to confirm. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/win_repo_clone.png?raw=true' width=50%> <br>
And if you navigate to the directory where you cloned the repository, you should see a folder with the name of the repository, as shown below:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/win_after_cloning.png?raw=true' width=50%> <br>

You can now open the repository in your IDE of choice and start working on it! 😃

<br><br>

#### Using Git in VScode
VScode has a built-in Git interface that allows you to manage your repositories. Let's go ahead and open the repository we just cloned in VScode. Open VScode, and click on the `Explorer` icon on the left - it looks like two files stacked on top of each other. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/vscode_with_cloned.png?raw=true' width=50%> <br>
If you now click on the Source Control icon (the one that looks like a set of circles joined by wires), you should see a screen like this (note that you may have to click on the "Manage Unsafe Repositories" button and select "Trust the authors" to manage the repository - this is, after all, a repository that you cloned from the internet from a user that you don't know):
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/vscode_source_control.png?raw=true' width=50%> <br>
Whenever you make changes to your repository, you will be able to push and pull changes using the buttons at the top of the screen. You can also use the `+` and `...` buttons to stage and commit changes.  
WE WONT BE GOING OVER HOW TO USE GIT IN THIS TUTORIAL, but you can find the documentation [here](https://code.visualstudio.com/docs/editor/versioncontrol).
Additionally, please don't try to push changes to the repository we cloned - it's not yours, and you don't have permission to do so. I'd also rather not to burden the repository owner with a bunch of pull requests from people who are just trying to learn how to use Git 😅.

<br><br>

#### Setting up GitHub Copilot in VScode

First, open up your Github account settings - you should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/github_settings.png?raw=true' width=50%> <br>
On the left column, you should see a link to `Copilot` under the `Code, Planning, and Automation` category. If you have a student account, you should be able to activate it for free so long as you subscribed to _Github Global Campus_ when setting up your account. (Alternatively, you can subscribe to it now by [following this link](https://education.github.com/discount_requests/application)) If you're not a student, you can still try it out for free with a trial, and at the time of writing the subscription is $10 a month.

Once your copilot license is active, go ahead and open up VSCode and head to the extensions tab. Search for `Copilot` and install the first result. You should see a screen like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/vscode_copilot_signin.png?raw=true' width=50%> <br>
On the left, you should see a user icon with a green dot next to it. Click on it and select the option to `sign in Github to use Github Copilot`. This will redirect you to an authorization screen that will look like this:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/authorize_vscode.png?raw=true' width=50%> <br>

Accept any prompts that pop up, and you should be good to go! 😃  
Now, whenever you are typing in a document within VSCode, you should see suggestions from Copilot pop up. You can accept these suggestions by pressing `Tab`.

Finally, you can sign up for the GitHub Copilot Chat Beta here (https://github.com/github-copilot/chat_waitlist_signup/join) if you're interested in trying it out. The chat interface allows you to have a convenient way of interacting with Copilot - for example, here is a quick conversation asking Copilot to make an LDA (linead discriminant analysis) model that fits 5 randomly generated features:  
<img src='https://github.com/tbeucler/2023_MLEES_JB/blob/5ed5b4cd553f414f01f4207ffb0523bfa1a93afc/ML_EES/Milton/Git/5-feature_LDA.png?raw=true' width=50%> <br>
Note that copilot can handle natural language requests, even with spelling mistakes! 😝
The full text of the code is:
```python
from sklearn.datasets import make_classification
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis

# Generate random dataset with 5 features
X, y = make_classification(n_samples=100, n_features=5, n_informative=3, n_redundant=0, n_classes=2, random_state=42)

# Fit LDA model to dataset
lda = LinearDiscriminantAnalysis()
lda.fit(X, y)
```