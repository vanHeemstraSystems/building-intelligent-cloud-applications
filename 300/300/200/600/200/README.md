# 200 - Create an Azure Functions project

Following the instructions found at https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python

Before you can publish your Functions project to Azure, you must have a function app and related resources in your Azure subscription to run your code. 

**The Function App provides an execution context for your functions.**

When you publish to a function app in Azure from Visual Studio Code, the project is packaged and deployed to the selected function app in your Azure subscription.

When you create a function app in Azure, you can choose either a quick function app create path using defaults or an advanced path. This way you have more control over the remote resources created.

As we have already created a Function App in previous steps, we can move forward.

**WARNING**: You will be installing a Python virtual environment later on, which requires you to install the following now up front to prevent errors:

```
$ sudo apt install python3.10-venv
```

The Functions extension lets you create a function app project, along with your first function. The following steps show how to create an HTTP-triggered function in a new Functions project. HTTP trigger is the simplest function trigger template to demonstrate.

1. Choose the Azure icon in the Activity bar, then in the **Workspace (local)** area, select the + button, choose **Create new project** in the dropdown.

2. Choose the directory location for your project workspace (in our case the current project "building-intelligent-cloud-applications") and choose **Select**. You should either create a new folder or choose an empty folder for the project workspace. Don't choose a project folder that is already part of a workspace.

3. When prompted, **Select a language** for your project, and if necessary choose a specific language version. Here we choose **Python**. When asked for a Python programming model choose **Model V2 (Recommended)**. Then when prompted for a Python interpreter to create a virtual environment choose **python3.10 3.10.12 (or the latest available)**.

4. Select the **HTTP trigger** function template, or you can select **Skip for now** to create a project without a function. You can always add a function to your project later. We won't skip, but select the HTTP trigger indeed.

5. Type **HttpExample** for the function name and select Enter, and then select **Function** authorization. This authorization level requires you to provide a function key when you call the function endpoint.

You will see a new project been created in your Workspace: **Local Project**

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