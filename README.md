# Creating a Python Function App with Poetry

A sample project that shows how to use Poetry in an Azure Function App. It includes local debugging in vscode and deployment with a Github Workflow.

## working with this sample

### locally

#### prerequisites

- [VSCode](https://code.visualstudio.com/)
- [Azurite](https://marketplace.visualstudio.com/items?itemName=Azurite.azurite) 
- [Python](https://www.python.org/downloads/)
- [Azure Functions Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Cisolated-process%2Cnode-v4%2Cpython-v2%2Chttp-trigger%2Ccontainer-apps&pivots=programming-language-python#install-the-azure-functions-core-tools)

Check the recommended extensions in this repo as well...

[extensions.json](./.vscode/extensions.json)


- Install the recommended extensions

- From the command prompt

```bash

git clone https://github.com/JayChase/func-py-with-poetry.git
cd func-py-with-poetry
poetry install
code .
```

- Run Azurite
    - in the terminal run `azurite`
    - or if you added the extension use the command palette (ctrl + shift + p *Azurite start*)

- Press ***F5*** to run and debug

### in a codespace

- Fork this repo and create a new codespace. Once everything has finished installing you should be ready to go

## essentials

- See the [launch.json](./.vscode/launch.json) and [tasks.json](./.vscode/tasks.json) how to run / debug a function app using poetry  

- [deploy.yml](./.github/workflows/deploy.yml) for how to build amd deploy the function app

- For a walkthrough of how the steps taken to create the project see this [blog post](https://www.usefuldev.com/post/Create%20a%20function%20app%20with%20poetry)

## references

- [Develop Azure Functions locally using Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Cisolated-process%2Cnode-v4%2Cpython-v2%2Chttp-trigger%2Ccontainer-apps&pivots=programming-language-python)

- [Poetry Docs](https://python-poetry.org/docs/)