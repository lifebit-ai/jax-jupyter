<p align="center">
  <img src="https://static.wixstatic.com/media/b34882_b300f090387248599125482b6750206c.jpg"  width="250" align="right" >
</p>

# Jupyter for Jax
*Hands-on workshop material for using Jupyter Notebooks on the CloudOS platform*
<br/>

<img src="img/cloudos_x_jupy.png"  width="600" align="center" >


## Agenda for the day:

<br/><br/>

| Time        | Programme       |
| ----------- | --------------------------------------------------------------------------- |
| 9:00-9:15   | :wave: Welcome Address - Dr. Anne Deslattes Mays / Dr. Maria Chatzou Dunford       |
| 9:15-9:30   | Demoing the end result                                                      |
| 9:30-10:00  | [1. Introduction to literate programming workflows with Jupyter Notebooks](https://github.com/lifebit-ai/jax-jupyter/blob/master/README.md#1-introduction-to-literate-programming-workflows-with-jupyter-notebooks)    |
| 10:00-10:10 | Configuration of Jupyter Notebooks on Lifebit CloudOS                       |
| 10:10-11:00 | [2. Exploratory Data Analysis Fundamentals with Pandas in Jupyter Notebooks](https://github.com/lifebit-ai/jax-jupyter/blob/master/README.md#2-exploratory-data-analysis-fundamentals-with-pandas---)     |
| 11:00-11:20 | :coffee: _Coffee Break_                                                              |
| 11:20-13:00 | [3. Interactive plotting with R in Jupyter Notebooks](https://github.com/lifebit-ai/jax-jupyter/blob/master/README.md#3-interactive-plotting-with-r-in-jupyter-notebooks)                           |
| 13:00-14:00 | :bento: _Lunch_                                                                     |
| 14:00-15:00 | [4. Will it reproduce? Revisiting a publication authored with Jupyter Notebooks](https://github.com/lifebit-ai/jax-jupyter/blob/master/README.md#4-will-it-reproduce-revisiting-a-publication-authored-with-jupyter-notebooks) |
| 15:00-15:20 | :coffee: _Coffee Break_                                                              |
| 16:00-16:45 | [5. Integrative Genomics Viewer on Lifebit CloudOS](https://github.com/lifebit-ai/jax-jupyter/blob/master/README.md#4-will-it-reproduce-revisiting-a-publication-authored-with-jupyter-notebooks)                             |
| 16:50-17:00 | :wave: _Closing Remarks_                                                           |

<br/><br/>


### 1. Introduction to literate programming workflows with Jupyter Notebooks on CloudOS


#### Set up your instance for version control

After you have forked the repository, `<USER_aka_you>/jax-jupyter`, click on <img src="img/clone_or_download.png"  width="85" align="center" > and click `SSH` to change the url.

#### Configuration of Jupyter Notebooks on Lifebit CloudOS


<details>
<summary>
Installing packages
</summary>

- with `pip`
- with `conda`

To add conda channels on our machine, go to [CloudOS](https://cloudos.lifebit.ai) and initialise a Jupyter Notebook session.

- Click `New analysis` > `Jupyter Session`
- Create a new Project by clicking `New` and name it `reproducible-paper.
- Choose an instance, for example `m1.xlarge` which has 4cpus and 15Gb RAM (it should be more than enough).

Once the instance has initialised, go to your Jupyter Notebook session and click on the top left corner `File` > `New` > `Terminal`.

This will open a terminal. Type the following commands to add conda channels, so that we can subsequently install libraries with conda:

```
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```
    
</details>



#### Jupyter Shortcuts Cheatsheet

WIP: Create markdown table for the most handy ones, here is a good place to start: http://maxmelnick.com/2016/04/19/python-beginner-tips-and-tricks.html


### 2. Exploratory Data Analysis Fundamentals with Pandas   <img src="https://pythonawesome.com/content/images/2018/05/pandas-logo.png"  width="80" align="center" >

Pandas is an excellent python library that simplifies basic data handling tasks for dataframes. In this part, we will explore a well known dataset, `iris`, and we will learn how to perform basic data cleaning and handling operations using pandas utilities along with python build in functions. We will use Pandas to read tabular files in a dataframe, inspect the dimensions, variable values and number of observations, create subsets of our data based on column and row filtering criteria and retrieve summary statistics for our dataset. In the end of this part, we will have created a basic exporatory data analysis workflow for performing a minimal data quality control routine.


#### Utils



<details>
<summary>
Basic built-in functions and methods that we will use:
</summary>

- `.type()`
- `.describe()`
- `.shape()`
- `.DataFrame()`

</details>



### 3. Interactive plotting with R in Jupyter Notebooks

For the second part of the workshop, we will switch to R to explore the great functionalities of `ggplot2` and related R packages for publication ready plots. We will first create a suitable input table with helper variable to facilitate the plotting. We will explore the ggplot layers and customise different aesthetics to  create publication ready plots. Finally, we will add interactivity to our plots by using the `plotly` library. We will also explore two extremely handy R packages, `ggpubr` and 



### 4. Will it reproduce? Revisiting a publication authored with Jupyter Notebooks

What does it take to submit a fully reproducible research piece? Notebooks, Jupyter Notebooks or Rmarkdown documents for example, have been proposed as a promising solution to accompany and bundle together in a reproducible report all the supplementary data of an scientific analysis that get published. Enabling other researchers reproduce our published work, offers the possibility of Postpublication Peer Review. During the Open Data Day 2017, hosted by SPARC and the NIH, within the two-day hackathon organised, an attempt to analyse [all Jupyter notebooks mentioned in PubMed Central](https://github.com/sparcopen/open-research-doathon/issues/25) started, with many contributors from the open source community, including [Daniel Mietchen](https://github.com/Daniel-Mietchen). Thanks to this initiative, a collection of metadata for publications including Jupyter Notebooks was created. At the time, approximately 100 publications from EuropePMC, which included Jupyter Notebooks to assist with reproducibility of their analysis were documented. Our goal for this part of the workshop is to select a publication with a Jupyter Notebook, and try to reproduce the analysis. The objective of this part is to realise the minimal requirements of a reproducible workflow and hopefully explore the literate programming workflow of the publication authors. The repository where this effort was coordinated can be found here: https://github.com/sparcopen/open-research-doathon. A relevant JupyterCon talk by [Daniel Mietchen](https://github.com/Daniel-Mietchen) can be also found here: https://youtu.be/Via7gBrjxHI


<details>
<summary>
Instructions:
</summary>


#### Step 1
Go to CloudOS and initialise a Jupyter Notebook session:

- Click `New analysis` > `Jupyter Session`
- Create a new Project by clicking `New` and name it `reproducible-paper.
- Choose an instance, for example `m1.xlarge` which has 4cpus and 15Gb RAM (it should be more than enough).

We don't need to select data because we are going to bring code and data from github. <img src="https://www.pngfind.com/pngs/m/40-405156_github-octocat-logo-black-and-white-transparent-github.png"  width="25" align="center" >
 

#### Step 2
Go to [RainCloudPlots/RainCloudPlots](https://github.com/RainCloudPlots/RainCloudPlots) and click [<img src="img/clone_or_download.png"  width="85" align="center" >](https://github.com/RainCloudPlots/RainCloudPlots) <br> Copy the link to the repository, we will need the link to clone it.

#### Step 3 
a) Go back to your Jupyter Notebook session and click on the top left corner `File` > `New` > `Terminal`.


b) Navigate to the `RainCloudPlots/tutorial_python/` folder in your Jupyter Lab session.  <br>
c) Find and click `raincloud_tutorial_python.ipynb` to launch the Jupyter Notebook.


#### Step 4

We are now ready to start reproducing the analysis, by running each cell of the Notebook.


#### Step 5
Make an issue and file the problems we have noticed

</details>

### 5. Integrative Genomics Viewer on Lifebit CloudOS  

Moving on to our last part of our tutorial, we will learn how to use Integrative Genomics Viewer (IGV) on the CloudOS platform and easily connect data from your cloud provider. Contrary to the usual configuration required to use IGV, there are no prerequisites or installation steps to use IGV on CloudOS, nor the need to copy data. To access data we will simply link the data from our cloud storage provider and continue with the IGV analysis.

