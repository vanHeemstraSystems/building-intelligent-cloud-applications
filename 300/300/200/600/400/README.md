# 400 - Deploy Project Files

Following instructions at https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python

**Note**: In order to Deploy Project Files, you first need to have created an Azure Functions Project. See building-intelligent-cloud-applications/300/300/200/600/200/README.md.

We recommend setting-up [continuous deployment](https://learn.microsoft.com/en-us/azure/azure-functions/functions-continuous-deployment) so that your function app in Azure is updated when you update source files in the connected source location. You can also deploy your project files from Visual Studio Code.

When you publish from Visual Studio Code, you take advantage of the [Zip deploy](https://learn.microsoft.com/en-us/azure/azure-functions/functions-deployment-technologies#zip-deploy) technology.

**WARNING**: Deploying to an existing function app always overwrites the contents of that app in Azure.

1. Choose the Azure icon in the Activity bar, then in the **Workspace** area, select your project folder and select the **Deploy...** button.

**Note**: When working from GitPod, and no Function Project shows in the Workspace area, you most likely did not create a Function Project yet. Go back to previous instructions and create a Function Project first. It will then show in your Workspace.

2. Select **Deploy to Function App...**, choose the function app you just created, and select **Deploy**.

3. After deployment completes, select **View Output** to view the creation and deployment results, including the Azure resources that you created. If you miss the notification, select the bell icon in the lower right corner to see it again.

## Generated Project Files

The project template creates a project in your chosen language and installs required dependencies. For any language, the new project has these files:

- **host.json**: Lets you configure the Functions host. These settings apply when you're running functions locally and when you're running them in Azure. For more information, see host.json reference.

- **local.settings.json**: Maintains settings used when you're running functions locally. These settings are used only when you're running functions locally. For more information, see Local settings file.

**WARNING**: Because the local.settings.json file can contain secrets, you need to exclude it from your project source control.

Depending on your language, these other files are created:

Files generated depend on the chosen Python programming model for Functions.

As we have chosen V2, the files are:

- A project-level **requirements.txt** file that lists packages required by Functions.

- A **function_app.py** file that contains both the function definition and code.

At this point, you can do one of these tasks:

- [Add input or output bindings to an existing function](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python#add-input-and-output-bindings).
- [Add a new function to your project](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python#add-a-function-to-your-project).
- [Run your functions locally](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python#run-functions-locally).
- [Publish your project to Azure](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python#publish-to-azure).