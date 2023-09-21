# 500 - Deploy Project Files

Following instructions at https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python

**Note**: In order to Deploy Project Files, you first need to have created an Azure Functions Project. See building-intelligent-cloud-applications/300/300/200/600/200/README.md.

We recommend setting-up [continuous deployment](https://learn.microsoft.com/en-us/azure/azure-functions/functions-continuous-deployment) so that your function app in Azure is updated when you update source files in the connected source location. You can also deploy your project files from Visual Studio Code.

When you publish from Visual Studio Code, you take advantage of the [Zip deploy](https://learn.microsoft.com/en-us/azure/azure-functions/functions-deployment-technologies#zip-deploy) technology.

**WARNING**: Deploying to an existing function app always overwrites the contents of that app in Azure.

1. Choose the Azure icon in the Activity bar, then in the **Workspace** area, select your project folder and select the **Azure Function** button (lightning).

**Note**: When working from GitPod, and no Function Project shows in the Workspace area, you most likely did not create a Function Project yet. Go back to previous instructions and create a Function Project first. It will then show in your Workspace.

2. Select **Deploy to Function App...**, choose the function app you just created, and select **Deploy**.

3. After deployment completes, select **View Output** to view the creation and deployment results, including the Azure resources that you created. If you miss the notification, select the bell icon in the lower right corner to see it again.
