# Python Environment, Virtual Machine, Docker Container and Git/GitHub

## 1. Introduction

This repository is created as part of a practical assignment about Python environment management, Virtual Machines, Docker Containers, and Git/GitHub.

The main objectives are:

- Understand Python Virtual Environments and environment management tools.
- Learn the basic concepts of Virtual Machines and Docker Containers.
- Practice creating and managing Python environments.
- Become familiar with Git and GitHub.
- Upload source code, documentation, and practical results to GitHub.

## 2. Repository Structure

```text
uv-demo/
│
├── 01_venv_pip/
│   ├── main.py
│   ├── requirements.txt
│   └── THEORY.md
│
├── screenshots/
│   └── CMD demonstration screenshots
│
├── src/
├── .gitignore
├── .python-version
├── pyproject.toml
├── README.md
└── uv.lock
```

## 3. Python Virtual Environment Demonstration

### 3.1. Tools and Environment

- Operating System: Windows
- Python Version: 3.10.11
- Environment Management: Python venv
- Package Manager: pip
- Python Library: NumPy 2.2.6
- Code Editor: Visual Studio Code

### 3.2. Create a Virtual Environment

A virtual environment was created using:

```bash
python -m venv .venv
```

The environment was activated using:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 3.3. Install Dependencies

NumPy was installed with a specific version:

```bash
pip install numpy==2.2.6
```

The installed packages were checked using:

```bash
pip list
```

The project dependencies were recorded in `requirements.txt`:

```text
numpy==2.2.6
```

### 3.4. Run the Python Program

The following program was created in `main.py`:

```python
import numpy as np

# Create a NumPy array
numbers = np.array([10, 20, 30, 40, 50])

# Perform calculations
print("Mang NumPy:", numbers)
print("Gia tri trung binh:", np.mean(numbers))
print("Tong cac phan tu:", np.sum(numbers))
```

Run the program:

```bash
python main.py
```

Expected output:

```text
Mang NumPy: [10 20 30 40 50]
Gia tri trung binh: 30.0
Tong cac phan tu: 150
```

### 3.5. Verify the Virtual Environment

The Python version was checked using:

```bash
python --version
```

The NumPy version was checked using:

```bash
python -c "import numpy; print(numpy.__version__)"
```

The Python interpreter location was checked using:

```bash
python -c "import sys; print(sys.executable)"
```

Installed packages were inspected using:

```bash
pip list
pip freeze
```

The virtual environment was deactivated using:

```bash
deactivate
```

After deactivation, the Python interpreter location was checked again to demonstrate the difference between the project environment and the outer environment.

### 3.6. Demonstration Results

The practical demonstration successfully showed:

- Creating an independent Python virtual environment.
- Activating and deactivating the environment.
- Installing NumPy using pip.
- Running a Python program using NumPy.
- Checking installed packages and their versions.
- Identifying the Python interpreter used by different environments.

## 4. Theory and Documentation

The theoretical concepts are documented in:

`01_venv_pip/THEORY.md`

The document covers:

1. Python Environment Management:
   - Virtual Environment
   - venv and virtualenv
   - pyenv
   - Conda
   - uv

2. Virtual Machine:
   - Definition and operating principles
   - Hypervisor Type 1 and Type 2
   - Advantages, disadvantages and applications

3. Docker Container:
   - Container concepts
   - Docker architecture
   - Docker Image and Container
   - Dockerfile and basic commands

4. Git and GitHub:
   - Version control concepts
   - Repository, Commit and Branch
   - Push, Pull and GitHub workflow

## 5. Git and GitHub

Git was used to manage project versions and GitHub was used to store the repository online.

The following commands were practiced:

```bash
git status
git add .
git commit -m "Update project"
git push
git pull
git log --oneline
```

The project was successfully uploaded to GitHub.

Repository: https://github.com/vuductienthanh/uv-demo

## 6. Conclusion

Through this assignment, I practiced creating and managing Python virtual environments, installing dependencies, running Python programs, and checking environment configurations.

I also became familiar with Git and GitHub for version control and source code submission.

The repository contains the practical Python demonstration, theoretical documentation, and screenshots of the implementation process.

