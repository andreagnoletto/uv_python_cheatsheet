# Install Ruff (On macOS and Linux)
curl -LsSf https://astral.sh/ruff/install.sh | sh

# Install Ruff (On Windows)
powershell -c "irm https://astral.sh/ruff/install.ps1 | iex"

# Install a specific version of Ruff
curl -LsSf https://astral.sh/ruff/0.7.2/install.sh | sh
powershell -c "irm https://astral.sh/ruff/0.7.2/install.ps1 | iex"

# Create a virtual environment with UV
uv venv --python 3.13

# Activate virtual environment
source .venv/bin/activate

# Add opencv-python
uv add opencv-python

# Remove opencv-python
uv remove opencv-python

# python version
uv python install 3.13
uv venv python 3.13

# cache only dependencies
uv run --with torch python_script.py

# add dependencies inline the code
uv add --script python_script.py "dynaconf" "rich"
uv run python_script.py

# falke8
uv tool install flake8
uv run flake8 python_file.py

# Run as formater
uv format python_file.py

# Run applications without installing Python and its libraries
uvx python_file.py 

# Interact with old applications that use only pip
uv pip install ...

# project.toml file content
[project]
name = "eyerot"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.11"
dependencies = [
    "opencv-python>=4.10.0.84",
]
