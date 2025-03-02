# cookiecutter-packages-automate-PyPI


[![image](https://img.shields.io/pypi/v/cookiecutter-packages-automate-PyPI.svg)](https://pypi.python.org/pypi/cookiecutter-packages-automate-PyPI)
[![image](https://img.shields.io/conda/vn/conda-forge/cookiecutter-packages-automate-PyPI.svg)](https://anaconda.org/conda-forge/cookiecutter-packages-automate-PyPI)


**A demo for building python packages using cookiecutter and update automatically via GitHub Actions, with version management through bump-my-version**


-   Free software: MIT License
-   Documentation: https://Liziye725.github.io/cookiecutter-packages-automate-PyPI
    

## How to Set Up 
1. **Create Project Structure** First, ensure that Cookiecutter is installed. Then, use the following command to create the project structure based on the template: ```bash cookiecutter gh:opengeos/cookiecutter-pypackage ``` This command will generate a new Python package project structure.
2. **Initialize Git Repository and Commit** Navigate to the project directory, initialize a Git repository, and commit the initial code: ```bash cd your-package-name git init git add . git commit -m "Initial commit" ```
3. **Create GitHub Repository** Create a new empty repository on GitHub. Do not initialize it with a README, license, or .gitignore file.
4. **Push Code to GitHub** Link your local repository to the GitHub repository and push the code: ```bash git remote add origin https://github.com/your-username/your-repo-name.git git branch -M main git push -u origin main ```
5. **Set Up GitHub Actions** The project contains multiple GitHub Actions workflow files (e.g., `docs-build.yml`, `docs.yml`, `installation.yml`) for automating various tasks. These workflows are located in the `.github/workflows` directory. For instance, the `pypi.yml` file defines the process for building and publishing the package to PyPI when a new release is created. Before using these workflows, you need to add your PyPI username and password as secrets in the GitHub repository settings: - `PYPI_USERNAME`: Set the value to `__token__` - `PYPI_PASSWORD`: Set the value to the API token obtained from PyPI This ensures that GitHub Actions can securely access and publish to PyPI.
6. **Version Management** The `bump-my-version` tool is used for managing the version of your project. With a simple command, you can bump the version and create a new Git tag. For example: ```bash bump-my-version patch git push origin main --tags ``` This command will increase the patch version number and push the changes to the remote repository. ## References - [Cookiecutter Official Documentation](https://github.com/cookiecutter/cookiecutter) - [bump-my-version Project Home](https://github.com/callowayproject/bump-my-version) - [opengeos/cookiecutter-pypackage Template](https://github.com/opengeos/cookiecutter-pypackage) By following the steps above, you can quickly set up a Python package using Cookiecutter and automate version management and publishing through GitHub Actions and `bump-my-version`.
