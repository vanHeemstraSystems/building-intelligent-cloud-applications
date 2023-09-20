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



More...
