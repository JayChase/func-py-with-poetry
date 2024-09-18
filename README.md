# Creating a Python Function App with Poetry

## Pre-requisites

- [VSCode](https://code.visualstudio.com/)
- [Azurite](https://marketplace.visualstudio.com/items?itemName=Azurite.azurite) 
- [Python](https://www.python.org/downloads/)

Check the recommended extensions in this repo as well...

[extensions.json](./.vscode/extensions.json)

## Project setup

- initialize the project

```bash

 poetry new func-py-with-poetry/

 code func-py-with-poetry

 git init
```

- clean out the poetry scaffolding folders

- create a function app

```bash
poetry run func init --python
```

- move the azure-functions requirement into poetry

```bash
poetry add azure-functions

rm requirements.txt
```

- add debugpy as a dev dependency

```bash
poetry add debugpy --group dev
```

- make sure the selected vscode interpreter is Poetry

- add a function

```bash
poetry run func new --template "Http Trigger" --name MyHttpTrigger -a ANONYMOUS
```

- check the function app run locally

```bash
poetry run func start
```

- add [tasks.json](./.vscode/tasks.json)

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "type": "shell",
            "label": "func: host start",
            "command": "poetry run func host start",
            "options": {
                "env": {
                    "languageWorkers__python__arguments": "-m debugpy --listen 127.0.0.1:9091"
                }
            },
            "problemMatcher": "$func-python-watch",
            "isBackground": true
        },
        {
            "label": "poetry install (functions)",
            "type": "shell",
            "osx": {
                "command": "poetry install"
            },
            "windows": {
                "command": "poetry install"
            },
            "linux": {
                "command": "poetry install"
            },
            "problemMatcher": []
        }
    ]
}
```

- add the [launch.json](./.vscode/launch.json)

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Attach to Python Functions",
            "type": "debugpy",
            "request": "attach",
            "connect": {
                "host": "localhost",
                "port": 9091
            },
            "preLaunchTask": "func: host start"
        }
    ]
}
```

- test out debugging the function in VSCode using **F5**

## References

- [Develop Azure Functions locally using Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Cisolated-process%2Cnode-v4%2Cpython-v2%2Chttp-trigger%2Ccontainer-apps&pivots=programming-language-python)

- [Poetry Docs](https://python-poetry.org/docs/)