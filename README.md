# FastAPI Template

## Prerequisites

Install `uv`.

- macOS and Linux:

    ```bash
    curl -LsSf https://astral.sh/uv/install.sh | sh
    ```

- Windows:

    ```powershell
    powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
    ```

## Run FastAPI APP

Use `uv` to install dependencies and run the app.

```bash
uv sync
uv run fastapi dev src/app/main.py
```

The FastAPI backend typically runs on `http://127.0.0.1:8000`. To use a different port, add `--port [PORT]`.

## Steps to Create Template

1. Create a `.python-version` file.

    ```bash
    echo "3.12" > .python-version
    ```

2. Define a `package` for module. As a FastAPI app is not executed by `python main.py`, so here init with `--lib`.

    ```bash
    uv init --lib --name app
    ```

3. Add FastAPI dependencies.

    ```bash
    uv add "fastapi[standard]"
    ```

3. Create a `main.py` under `./src/app/`.

    ```python
    from fastapi import FastAPI

    app = FastAPI()


    @app.get("/")
    async def root():
        return {"message": "Hello World"}
    ```
