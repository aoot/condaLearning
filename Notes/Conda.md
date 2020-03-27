# Conda Notes

## Definition
- Powerful package manager
- Environment manager

## Managing Environments
- Default environment name "base"

```bash
# Name the new environment snowflakes and install the package biopython
conda create --name snowflakes biopython
```
   - Name the environment **snowflakes** and install the package **BioPython**

```bash
# List of all the conda environments
conda info --envs  # List of all of the environments
conda activate  # Changing the current environment

# Contact environment management (create and activate environment)
conda create --name snakes python=3.5 # Create a new environment named snakes that contains Python3.5
conda activate snakes # To activate the snakes environment

# Conda package management [of the activated environment]
conda list # Check the list of packages in the acitvated environment
conda search beautifulsoup4 # Search if beautifulsoup4 is available from Anaconda repository
conda install beautifulsoup4 # Installs the package
```

### Python
  - System Python
  - Python installation from source such as the macOS Homebrew package manager
  - Globally installed package from pip such as panda and NumPy
  - **Let the conda installation of Python to your PATH environment variable** There is no need set the PYTHONPATH environment variable

### PATH Variable
  - See Python variable in your PATH variable
    - Windows: ```bash echo %PATH% ```
    - macOS / Linux: ```bash echo $PATH ```
  - Which Python installation is currently set as the default
    - Windows: ```bash where python ```
    - macOS / Linux: ```bash which python ```

### Create an environment from file
```bash
# Create an environment from yml file
conda env create -f environment.yml

# Removing an environment
conda remove --name myenv --all

# Export active environment into yml file
conda env export > environment.yml

# Creating an environment file manually
[Tutorial](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#create-env-file-manually)

```
[Conda Cheatsheet](https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf)
