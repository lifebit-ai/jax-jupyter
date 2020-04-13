# 1.Start a new Jupyter Lab session in CloudOS

For detailed instructions on how to access the Jupyter Notebook Sessions in Lifebit CloudOS, take a look at the documentation here:
https://lifebit.gitbook.io/cloudos/web-interface/jupyter-lab

Follow the instructions on ["How to create a Jupyter Notebook Session in CloudOS"](https://lifebit.gitbook.io/cloudos/web-interface/jupyter-lab#how-can-i-create-a-new-notebook-sessions-on-cloudos). For this step of the analysis, start a small sized instance. 4vCPUS instances for example are sufficient for exploratory data analysis tasks with small datasets.

# 2. Prepare your environment for using `conda`

After your Notebook Session has initilased in CloudOS, open a terminal using the + icon, and type the following command to initialize conda for shell interaction:

```bash
conda init
``` 

Close the terminal and open a new one so that the changes take effect.


# 3. Clone the tutorial's GitHub repo in the Jupyter Notebook Session

To bring the code from GitHub to CloudOS, we will use the `git clone` command. Follow the steps below to:

a) configure your Git credentials in the Jupyter Notebook Session
b) clone the repository in your working directory in the Jupyter Notebook Session

> **NOTE**:
If you have 2 Factor Authentication enabled in your GitHUb account, make sure you have handy your personal access token. If not, you can use your GitHub password ot login.
If you want to create a Personal Access Token (PAT) with sensible defaults, an easy way is to call the `browse_github_pat()` function from the R package {usethis}.

```R
usethis::browse_github_pat()
```

This command will take you to the following webpage:
https://github.com/settings/tokens/new?scopes=repo,gist,user:email&description=R:GITHUB_PAT

You can see in the URL the default scopes. Follow the instructions in your GitHub account to complete the creation of the Personal Acces Token.

## 3a) Configure your Git credentials in the Jupyter Notebook Session

Next, let's set up our Git credentials in the Jupyter Notebooks Session to be able to perfom git commands, like `git push`, `git pull`, `git add` etc.

To configure your `user.name`, `user.email` and favorite text editor execute the following commands.
Replace the example `user.name` and `user.email` with your respective information that you have associated with your GitHub account.

```bash

# Set user name and email
git config --global user.name 
git config --global user.email 

# Set your prefered editor
git config --global core.editor nano 
```

You can swap `nano`, for `vi`, `vim` or `emacs`.

## 3b) Clone the repository in your working directory in the Jupyter Notebook Session

The default working directory in the CloudOS Jupyter Notebooks Session is named `session_data`. Go ahead and clone the repo in the `session_data` directory by typing the following command in your terminal:

```bash
git clone https://github.com/lifebit-ai/jax-jupyter.git
```

Then, `cd` into the `jax-jupyter` directory

```bash
cd jax-jupyter/
```

# 4. Update the `base` conda environment


Use the dependencies metadata file named `environment.yml` to install the required dependencies for the turorial. 

> **NOTE**:
You can read more about installing dependencies with conda from metadata files in the official documentation [here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file).

To install the required dependencies, type the following commands:

```bash
conda env update --name base --file dependencies/environment.yml -y
conda activate base
```
*TIP:*

During the tutorial, we might install more R packages. In the end of our Jupyter Notebook Session, we can export the *updated* environment metadata in a file (it is typical to name this `environment.yml`) and use it to reproduce the same workspace in the future or share it with someone that wants to test the same tutorial.

A handy command to export conda dependencies installed during the session in [an OS agnostic manner](https://github.com/conda/conda/issues/9399) is the following:

```bash
 conda env export --no-builds --from-history  | grep -v "^prefix: " > environment.yml
```

# 5. Ready!

Once conda has successfully installed the dependencies, your environment is ready.
We can now start working on our Jupyter Notebook Sessions!