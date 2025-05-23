<img align="right" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Gnu-bash-logo.svg/500px-Gnu-bash-logo.svg.png" alt="Bash Logo" width="100">

# Fast Project Setup Using a Bash Script
Welcome to the Nova SBE Tech Club! This notebook explains how to quickly set up a structured data science project using a simple Bash script.

---

## Why Use a Bash Script?

- **Consistency:** Ensures a uniform project structure across all team members.
- **Efficiency:** Saves time by automating repetitive setup tasks.
- **Reproducibility:** Makes it easy to recreate project environments.

Let's walk through the process!

## Step 1.1: 

### Local Repository Construction (No git):

The first step is to try and create a local repository without using git. This is useful for setting up a project structure quickly without the need for version control. It can also be used for other purposes such as creating a folder structure for a new project or organizing files.

>"Create Your Bash Script File (`setup_project.sh`) in the directory where you want to create the folder structure. Then proceed to [Step 2:](#step-2:) to se the instructions how to run it.

Below is a Bash script that will generate our comprehensive project structure including conda environment and folder structure:

<details>
<summary>Bash</summary>

```bash
#!/bin/bash

PROJECT_NAME="Nova_SBE_Tech_Club_TS_Analysis"

mkdir -p $PROJECT_NAME
cd $PROJECT_NAME

mkdir -p data/{raw,processed}
mkdir -p notebooks/{exploratory,modeling}
mkdir -p outputs/figures
mkdir -p models
touch README.md requirements.txt

mkdir -p src/{eda,analysis,features,preprocessing,labels,dataset,modeling}
mkdir -p tests/unit

touch src/eda/trend_visualizer.py
touch src/analysis/time_series_inspector.py src/analysis/causal_explorer.py
touch src/features/feature_engineer.py
touch src/preprocessing/feature_preprocessor.py
touch src/labels/label_analyzer.py
touch src/dataset/dataset_builder.py
touch src/modeling/model_evaluator.py src/modeling/anomaly_detector.py

cat <<EOT >> requirements.txt
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
featuretools
scikit-learn
pca
jupyter
pytorch-lightning
streamlit
plotly
pydantic
EOT

echo "Project structure for $PROJECT_NAME created successfully!"
```

</details>


## Step 1.2: 

### Quick Git Repository Construction

In this step, you can see how to create a local repository from a remote Git repository. This is useful for setting up a project structure quickly while also using version control. It can also be used for other purposes such as creating a folder structure for a new project or organizing files.

>Create Your Bash Script (`setup_project.sh`) to setup a local only repository from remote Git repository. Then proceed to [Step 2:](#step-2:) to se the instructions how to run it.

Below is a Bash script that will generate our comprehensive project structure by initializing a local git repository, setting up folders and creating a conda environment:

<details>
<summary>Bash</summary>

```bash
#!/bin/bash

# === CONFIGURATION ===
REPO_URL="git@github.com:YourGitUserName/My_wonderful_Project.git"
ENV_NAME="my_new_conda_env"

# === UTILITY ===
echo "🚀 Starting setup..."

# Clone repository
git clone "$REPO_URL"
REPO_DIR=$(basename "$REPO_URL" .git)
cd "$REPO_DIR" || { echo "❌ Failed to enter repo directory"; exit 1; }

# Ensure conda is available in script
if ! command -v conda &> /dev/null; then
    echo "❌ Conda is not found. Please ensure Miniconda/Anaconda is installed and accessible."
    exit 1
fi

# Activate conda in shell context
source "$(conda info --base)/etc/profile.d/conda.sh"

# Create & activate environment
if conda info --envs | grep -q "$ENV_NAME"; then
    echo "🔁 Conda environment '$ENV_NAME' already exists. Skipping creation."
else
    echo "📦 Creating conda environment '$ENV_NAME'..."
    conda create -n "$ENV_NAME" python=3.10 -y
fi

echo "⚡ Activating environment '$ENV_NAME'..."
conda activate "$ENV_NAME"

# Project folder structure
echo "📁 Creating folder structure..."
mkdir -p data/{raw,processed}
mkdir -p notebooks/{exploratory,modeling}
mkdir -p outputs/figures
mkdir -p models
mkdir -p src/{eda,analysis,features,preprocessing,labels,dataset,modeling}
mkdir -p tests/unit

# Boilerplate files
echo "📄 Creating source files and README..."
touch README.md
touch src/eda/trend_visualizer.py
touch src/analysis/time_series_inspector.py src/analysis/causal_explorer.py
touch src/features/feature_engineer.py
touch src/preprocessing/feature_preprocessor.py
touch src/labels/label_analyzer.py
touch src/dataset/dataset_builder.py
touch src/modeling/model_evaluator.py src/modeling/anomaly_detector.py

# Create requirements.txt
echo "🧾 Writing requirements.txt..."
cat <<EOT > requirements.txt
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
featuretools
scikit-learn
pca
jupyter
pytorch-lightning
streamlit
plotly
pydantic
EOT

# Install dependencies
echo "📦 Installing dependencies..."
pip install -r requirements.txt

echo "✅ Setup complete!"
echo "🔧 Project: $REPO_DIR"
echo "🌱 Conda Environment: $ENV_NAME"


```
</details>


## Step 2: 

### Run Your Bash Script

✅ How to Use It
1. Save the script as setup_project.sh

2. Make it executable:

```bash
chmod +x setup_project.sh
```

`chmod +x` ensures the script is executable by the system.

3. Run the script

```bash
./setup_project.sh
```

>⚠️ Just remember: for Conda activate to work, your terminal must already have Conda initialized (which is done during Conda installation or via source like shown above).

Your project folder (`My_wonderful_Project`) will be set up instantly.


## Step 3 

### Inspect Your New Project Structure

Let's verify the structure created:

```bash
tree My_wonderful_Project
```

You should see the neatly organized folders and files ready for your data analysis journey.

## Step 4: 

### Next Steps

You can now:
- Set up a Python environment.
- Install dependencies:

```bash
pip install -r requirements.txt
```

Enjoy structured, efficient project development with Nova SBE Tech Club!

---

**Happy coding! 🚀**
