---
title: 'Prepretions on Server for Projects'
date: 2023-10-11T20:11:33+08:00
draft: false
tags: ["html", "css"]
categories: ["tech"]
---



# Step 1: Download and install Anaconda/Miniconda

Conda is a popular package, dependency, and environment management system, particularly useful for Python and other programming languages. It allows you to easily install and manage multiple environments, each with its own set of packages and dependencies. More details are in [conda documents](https://docs.conda.io/en/latest/). You can download it on this [link](https://docs.conda.io/projects/miniconda/en/latest/).


<details>
<summary>Common Conda Commands</summary>

```bash
# This command line will tell you if 'conda' is in your system' PATH
which conda
# If conda is installed and on your PATH, this command will return the path to the conda executable. If nothing is returned, then conda might not be installed or not be in your PATH.

# display the version of 'conda' installed on your system
conda --version

# Common Conda Commands
# Update conda to the latest version
conda update conda

# Create a new environment named 'myenv' with Python 3.8
conda create --name myenv python=3.8

# Acativate an environment
conda activate myenv

# Deactivate the current environment
conda deactivate

# List all environments
conda env list
conda info --envs

# Install some packages (ex: numpy) in the current environment
conda install numpy

# List packages in the current environment
conda list

# Remove an environment
conda env remove --name myenv

# Update a package
conda update numpy

# Get information about the conda environment
conda info

# Conda has a comprehensive list of commands and options that you can explore further in its official documentation or by using
conda --help
```
</details>