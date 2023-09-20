# 300 - Get the URL of an HTTP triggered function in Azure

Following the instructions at https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python

To call an HTTP-triggered function from a client, you need the URL of the function when it's deployed to your function app. This URL includes any required function keys. You can use the extension to get these URLs for your deployed functions. If you just want to run the remote function in Azure, [use the Execute function now](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python#run-functions-in-azure) functionality of the extension.

1. Select F1 to open the command palette, and then search for and run the command **Azure Functions: Copy Function URL**.

2. Follow the prompts to select your function app in Azure and then the specific HTTP trigger that you want to invoke.

The function URL is copied to the clipboard, along with any required keys passed by the ```code`````` query parameter. Use an HTTP tool to submit POST requests, or a browser for GET requests to the remote function.

When the extension gets the URL of functions in Azure, it uses your Azure account to automatically retrieve the keys it needs to start the function. [Learn more about function access keys](https://learn.microsoft.com/en-us/azure/azure-functions/security-concepts#function-access-keys). Starting non-HTTP triggered functions requires using the admin key.