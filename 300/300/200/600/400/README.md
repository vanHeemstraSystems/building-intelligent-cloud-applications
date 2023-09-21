# 400 - Deploy Project Files

Following instructions at https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=node-v3%2Cpython-v2%2Cin-process&pivots=programming-language-python

We recommend setting-up [continuous deployment](https://learn.microsoft.com/en-us/azure/azure-functions/functions-continuous-deployment) so that your function app in Azure is updated when you update source files in the connected source location. You can also deploy your project files from Visual Studio Code.

When you publish from Visual Studio Code, you take advantage of the [Zip deploy](https://learn.microsoft.com/en-us/azure/azure-functions/functions-deployment-technologies#zip-deploy) technology.

**WARNING**: Deploying to an existing function app always overwrites the contents of that app in Azure.

1. Choose the Azure icon in the Activity bar, then in the **Workspace** area, select your project folder and select the **Deploy...** button.

**Note**: When working from GitPod, your project won't show in the Workspace area. As a work-around you can just click the Azure Function icon (lighting) which will provide you with the option to ```Deploy to function App```. It will give you a dropdown list to select your folder to deploy, which includes the root directory of your GitPod workspace. Choose that one to start the deployment.



More ...
