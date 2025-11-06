🐍 Using uv with Python 3.13
1. Install uv
```shell
pip install uv
```

2. Create a New Project
```shell
uv init myproject --python 3.13
```

3. Activate the Environment
```shell
cd myproject
uv venv activate
```

(Or use uv run to execute commands without manual activation.)

4. Verify Python Version
```shell
uv run python --version
```

5. Add Dependencies
```shell
uv add requests
```

6. Run Your Script
```shell
uv run python app.py
```
