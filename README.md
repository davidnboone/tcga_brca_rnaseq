# Differential Expression Analysis using DESeq2 on RNAseq data from TCGA
This jupyter notebook is written for use with an R kernel.

The notebook details steps from locating publically-available RNAseq counts, abundance, and clinical data from TCGA through identification of differentially expressed genes with DESeq2 and the visualization of th results.

Content is provided in the form of Jupyter notebooks. If you need an introduction to Jupyter, you can see the official [documents](https://jupyter.org/).

You can run these notebooks on a jupyterhub server - potentially one provided by your course - or on your own computer, appropriately configured Python, R, an RKernel, and appropriate R libraries (installed through the first notebook).

## 1. Installing the appropriate Jupyter configuration on your computer
For new users, I highly recommend installing Jupyter through Anaconda following these [instructions](https://jupyter.readthedocs.io/en/latest/install.html) and installing the latest version of Python 3.x.

For this particular assignment, you will also need R. You can download and find installation instructions [here](https://www.r-project.org/).

After R is installed, it needs to be configured for Jupyter to establish an RKernal. You can do this by installing an [RKernal](https://irkernel.github.io/installation/). Follow the instructions on the page and be sure to launch R from the command line instead of the app icon. Installation of the RKernal will fail if you launch from the app icon.


**note** For R projects, I highly recommend using [RStudio](https://www.rstudio.com/products/rstudio/download/) and RMarkdown instead of Jupyter Notebooks, but that will not be required to complete this module, which was written in Jupyter for purpose of instruction.

## 2. Create a github or gitlab account (these instructions are copied from [this](https://github.com/dbmi-pitt/SocialMediaDataScience#1-access-your-jupyter-configuration) readme.
Github and GitLab are two popular community sites based on the Git source-code control system. We're going to use Git to create your own local copy of these modules, and to store any changes. We'll tell you a bit about it here, but there's much more to learn - for more information on Git, see [git-scm.com](https://git-scm.com/).

For now, go to either [Github](https://github.com/) or [GitLab](https://about.gitlab.com/) and create an account. Remember your account name.

## 3. Create a new repository in your GitHub or GitLab.com
The Jupyter notebook exercises for this module are contained in a GitHub repository - a collection of related files managed using the Git source code control system. To do your work for these modules, you will need your own personal copy of this repository stored in your GitHub or GitLab account. Below, we give different descriptions for GitHub and GitLab.

### 3.1 If you are using GitHub
To do this in GitHub will require three browser windows:

1. The first should be pointed at the GitHub.com repository that this file is in. You're probably on that page right now as you read this file.
2. The second window should be on your Jupyter notebook or JupyterLab home page.

Once this is setup, we can go to work.

1. In the window on your GitHub repository page, press the "fork" button, found just below your avatar and user name in the title bar. It will ask you "Where should we fork this repository?". Choose the selection corresponding to your GitHub user name. The system will ask you to wait, and it will point you to a new page with a copy of this repository under your account. This is now your repository to use as you will, without any fear of damaging the main repository.
2. On this page, there is a "Clone or download" [button](https://github.com/dbmi-pitt/SocialMediaDataScience/blob/master/images/fork-clone.png). Click on this button and copy the link that shows up. You will need this URL in step 5.

### 3.2 If you are using GitLab
1. Go to your GitLab homepage.
2. Click "+" in the top menu bar.
3. Select "New Project"
4. Click "Import Project" and then "Git Repo by URL"
5. At the top of the page containing this document, click on "Clone or download". Copy this URL
6. Paste this URL into the "Git repository URL" textbook on the GitLab import page.
7. Click "create project". You can keep the repository to start.
8. You'll see a message indicating that something is happening.
9. When it is done, go to your home page. You should see a new repository. Go to the home page of that repository. There will be a box under the repository title that says "SSH" with a URL next to it. Click on the "SSH" button to change it to "HTTPS".
10. Copy the URL next to the "HTTPS" button. You will need this URL in step 5.

## 4. Clone the repository
At this point, you should have the URL for your own personal copy of this repository. You will now need to clone it into your Jupyter environment.

1. Go to your Jupyter home page (the easiest way to do this is to use the command ```jupyter notebook``` from the command prompt). Click "New" on the top right, and select ["Terminal"](https://github.com/dbmi-pitt/SocialMediaDataScience/blob/master/images/new-terminal.png). This will create a linux command-line terminal window in the browser. Alternatively, if you are using JupyterHub, press the "Terminal" button in the Launcher screen.
2. run "git clone .." followed by the URL of your repository. You will need to provide your GitHub or GitLab user name and password.
3. In a new browser tab (or in an existing browser tab if you already have it open), go to the home page of your Jupyter environment. You will see a new directory, likely entitled "rnaseq-tcga". This is where you will do your work. If you are using JupyterLab, this directory will appear in the file browser on the left.

## 5. Start a Jupyter notebook and do your work

If everything is appropriately installed and cloned you should be able to run the notebooks.

Finish reading the rest of this readme and then when ready click on the notebooks to open them and start. Be sure to choose the RKernel. 

This assignment is broken into 4 different python notebooks. Do them in order. Notebooks 2-4 have optional steps at the beginning of each in case you do not continue directly from the previous notebook. The 4 notebooks are:

**1. RNASeq_TCGA_Introduction_Download** - In the first notebook, we will:
- a) learn about RNA sequencing technology, analysis pipelines, sources of data, and about a specific question we will answer through these notebooks. The question is what are the differentially expressed genes between the HER2+ and TNBC subtypes of breast cancer.
- b) install all of the necessary R packages to complete this assignment. If installations fail for any of the packages, please follow the documentation at their respective websites to correct. Contact your instructor if issues remain. 
- c) Download and decompress all the data.

**2. Data wrangling - Prepping raw clinical and transcript counts data to generate gene level data for DEseq2 using tximport** - In this lesson, you will do all of the data wrangling necessary to run DESeq2 to answer our question. This includes:
- a) Extract and calculate HER2 and TNBC status of each sample.
- b) Extract count and abundance data from those samples.
- c) The count and abundance data is transformed and currently at the transcript level, so we will need to untransform and collapse to gene level to perform the differential expressional analysis. In this notebook we will prep the data into the proper form to collapse into gene level.

**3. Running Tximport and DESeq2** - In this lesson, you will perform the differential gene expression analysis. This includes:
- a) Run Tximport, which will collapse count and abundance data to the gene level.
- b) Calculate differentially expressed genes using DESeq2.

**4. Visualize and Annotate DESeq2 results** - In this lesson, you will annotate, export, and visualize the results. This includes:
- a) Annotate the results table to include GeneSymbol and information about abundance
- b) Visualize the results with a few QC plots
- c) Generate a heatmap of filtered DEGs









