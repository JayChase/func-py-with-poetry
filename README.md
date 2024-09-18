# Creating a Python Function App with Poetry

## Pre-requisites

VSCode

Azurite 
Python



## Project setup

```bash

 # initialize the project

 poetry new func-py-with-poetry/

 code func-py-with-poetry

 git init

 # clean out the scaffolding 

 poetry run func init --python

# move the azure-functions requirement into poetry 

poetry add azure-functions

rm requirements.txt

# add debugpy as a dev dependency

poetry add debugpy --group dev

# make sure the selected vscode interpreter is Poetry
 
# add a function
poetry run func new --template "Http Trigger" --name MyHttpTrigger -a ANONYMOUS

 # check the function app run locally
poetry run func start

# add the launch.json and tasks.jon 

# test out debugging the function in VSCode using F5



```

## References

- [Develop Azure Functions locally using Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Cisolated-process%2Cnode-v4%2Cpython-v2%2Chttp-trigger%2Ccontainer-apps&pivots=programming-language-python)

- [Poetry Docs](https://python-poetry.org/docs/)