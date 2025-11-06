🐍 Using uv with Python 3.13
1. Install uv
pip install uv

2. Create a New Project
uv init myproject --python 3.13

3. Activate the Environment
cd myproject
uv venv activate


(Or use uv run to execute commands without manual activation.)

4. Verify Python Version
uv run python --version
# Python 3.13.x

5. Add Dependencies
uv add requests

6. Run Your Script
uv run python app.py
