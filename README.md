# fewshot

This package reserves the `fewshot` name for the Fewshot project.

- Pypi: https://pypi.org/project/few-sh/

- Homepage: https://github.com/few-sh/fewshot

> Temporary placeholder: functionality will be added in future releases.

## Publishing to PyPI

This project uses `uv` for environment management and `twine` for publishing. The following steps outline the manual publishing process.

1.  **Set up the environment:**
    If you haven't already, create and activate a virtual environment.
    ```sh
    uv venv
    source .venv/bin/activate
    ```

2.  **Install tools:**
    Install `build` and `twine`.
    ```sh
    uv pip install build twine
    ```

3.  **Build the package:**
    This will create the distribution files in the `dist/` directory.
    ```sh
    python3 -m build
    ```

4.  **Create an API Token:**
    - Create a `.env` file in the root of the project.
    - Add your PyPI API key to the file. This key should be scoped to the `few-sh` project.
      ```
      PYPI_API_KEY=pypi-your-api-key
      ```

5.  **Publish the package:**
    Run the `twine` upload command. This command securely loads your API key from the `.env` file.
    ```sh
    export TWINE_USERNAME=__token__
    export TWINE_PASSWORD=$(grep PYPI_API_KEY .env | cut -d '=' -f2)
    twine upload dist/*
    ```
