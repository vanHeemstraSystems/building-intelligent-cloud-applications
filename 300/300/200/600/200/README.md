# 200 - Create an Azure Functions project

Following the instructions found at https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python

Before you can publish your Functions project to Azure, you must have a function app and related resources in your Azure subscription to run your code. 

**The Function App provides an execution context for your functions.**

When you publish to a function app in Azure from Visual Studio Code, the project is packaged and deployed to the selected function app in your Azure subscription.

When you create a function app in Azure, you can choose either a quick function app create path using defaults or an advanced path. This way you have more control over the remote resources created.

As we have already created a Function App in previous steps, we can move forward.

The Functions extension lets you create a function app project, along with your first function. The following steps show how to create an HTTP-triggered function in a new Functions project. HTTP trigger is the simplest function trigger template to demonstrate.

1. Choose the Azure icon in the Activity bar, then in the **Workspace (local)** area, select the + button, choose **Create Function** in the dropdown. When prompted, choose **Create new project**.

More ...