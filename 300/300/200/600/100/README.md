# 100 - Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/) installed on one of the [supported platforms](https://code.visualstudio.com/docs/supporting/requirements#_platforms). **Note**: We like to use "GitPod" to have an on-demand Visual Studio Code instance to develop from.
- [Azure Functions extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions). You can also install the [Azure Tools extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack), which is recommended for working with Azure resources.
- An active [Azure subscription](https://learn.microsoft.com/en-us/azure/guides/developer/azure-developer-guide#understanding-accounts-subscriptions-and-billing). If you don't yet have an account, you can create one from the extension in Visual Studio Code.

- Add [Azure Account extension], which will be automatically installed when installing the Azure Functions extension.

Of all the above Visual Studio Code extension, it is recommended to add them also to your ```.gitpod.yml``` file so they will be automatically installed when you spin up a new Gitpod environment. Remember to commit the ```.gitpod.yml`` file to your repository.

```
vscode:
  extensions:
    - ms-azuretools.vscode-azurefunctions
    - ms-vscode.azure-account
```
.gitpod.yml

## Run local requirements

These prerequisites are only required to [run and debug your functions locally](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python#run-functions-locally). They aren't required to create or publish projects to Azure Functions.

- The [Azure Functions Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local), which enables an integrated local debugging experience. When using the Azure Functions extension, the easiest way to install Core Tools is by running the ```Azure Functions: Install or Update Azure Functions Core Tools``` command from the command pallet (Open command pallet from the hamburger menu: View > Command Pallet, or use Control + Shift + P keyboard shortcut).

- [Python](https://www.python.org/downloads/), one of the [supported versions](https://learn.microsoft.com/en-us/azure/azure-functions/functions-reference-python#python-version). Check if Python is installed as follows: ```$ python3 --version```

- [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) for Visual Studio Code.

Your .gitpod.yml file should now contain:

```
vscode:
  extensions:
    - ms-azuretools.vscode-azurefunctions
    - ms-vscode.azure-account
    - ms-python.python
```

.gitpod.yml

**WARNING**: Functions doesn't currently support Python function development on ARM64 devices. To develop Python functions on a Mac with an M1 chip, you must run in an emulated x86 environment. To learn more, see [x86 emulation on ARM64](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local#x86-emulation-on-arm64).
