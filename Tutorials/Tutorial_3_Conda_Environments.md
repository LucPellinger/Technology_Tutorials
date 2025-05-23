
<img align="right" src="https://www.anaconda.com/wp-content/uploads/2022/12/anaconda_secondary_logo.svg" alt="Anaconda Logo" width="200">

# Creating & Managing Conda Environments

Using Conda environments helps isolate project dependencies, ensuring reproducibility and avoiding conflicts with other projects.

## Step 1: Installing Conda

If you haven't installed Conda yet, you can download and install it from the official Anaconda or Miniconda website:

- [Anaconda](https://www.anaconda.com/products/distribution)
- [Miniconda](https://docs.conda.io/en/latest/miniconda.html)

Follow the installation instructions provided for your operating system.

---

## Step 2: Creating a Conda Environment

In the following steps, we will create a new Conda environment named `image_classification` with Python 3.10.

### Create from scratch:

```bash
conda create -n image_classification python=3.10
```

### Activate environment:

```bash
conda activate image_classification
```

---

## Step 3: Installing Dependencies

### From a `requirements.txt` file (pip):

```bash
pip install -r requirements.txt
```

### From an `environment.yml` file (Conda):

```bash
conda env create -f environment.yml
```

### Install individual packages:

```bash
conda install numpy pandas matplotlib
pip install streamlit plotly
```

---

## Step 4: Managing and Modifying Environments

### List all environments:

```bash
conda env list
```

### View packages in an environment:

```bash
conda list
conda list -n image_classification
```

### Update the environment:

```bash
conda update --all
```

### Add packages to an existing environment:

```bash
conda install seaborn scikit-learn
```

### Update environment from updated `environment.yml`:

```bash
conda env update --file environment.yml --prune
```

### Deactivate environment:

```bash
conda deactivate
```

### Delete an environment:

```bash
conda remove --name image_classification --all
```

---

## Exporting and Sharing Environments

Export your current environment:

```bash
conda env export > environment.yml
```

This file can then be shared and used to recreate the environment.

---

## Conda Channels

Channels allow you to install packages maintained by different communities:

- **Install from specific channel:**
```bash
conda install -c conda-forge package_name
```

- **Add channel permanently:**
```bash
conda config --add channels conda-forge
```

---

## General Useful Conda Commands

- Check Conda version:
```bash
conda --version
```

- Search for a package:
```bash
conda search package_name
```

- Clean unused packages:
```bash
conda clean --all
```

---

## Next Steps

Now you're equipped to manage and scale your project environments using Conda. Use these tools to ensure clean, reproducible setups in your data science or AI engineering workflows.

---

**Happy coding! 🚀**
