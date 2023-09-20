building-intelligent-cloud-applications
# Building Intelligent Cloud Applications

Based on the book "Building Intelligent Cloud Applications" by O'Reilly

## 100 - Introduction

This repository documents and stores files that are part of the content of the book "Building Intelligent Cloud Applications".

## 200 - Requirements

- A subscription with Microsoft Azure: https://portal.azure.com/#@wvanheemstraicloud.onmicrosoft.com/resource/subscriptions/c1681d0d-f8cc-4263-a75b-019e7a37f96f/overview

## 300 - Building Our Application

### 100 - Azure Dashboard

Browse to https://portal.azure.com/#home for the Azure Dashboard.

Now create a new resource by in the panel left, click "Create a resource".

Then in the list of resources that opens, select Function App: Create.

For Subscription choose: Pay-As-You-Go

For Resource Group create a new resource group with the following settings:

|Setting|Value|
|--|--|
|Subscription|Pay-As-You-Go|
|Resource Group|python-faas|
|Function App name|python-faas.azurewebsites.net|
|Deploy as|Code|
|Runtime stack|Python|
|Version|3.10|
|Region|West Europe|
|Operating System|Linux|
|Hosting|Consumption (Serverless)|

Choose **Next:Storage >**

|Setting|Value|
|--|--|
|Storage Account|pythonfaasbc70 note:autogenerated|

Choose **Next:Networking >**

|Setting|Value|
|--|--|
|Enable Public Access|On|
|Enable Network Injection|Off|

Choose **Next:Monitoring >**

|Setting|Value|
|--|--|
|Enable Application Insights|Yes|
|Application Insights|python-faas (West Europe)|
|Region|West Europe|

Choose **Next:Deployment >**

|Setting|Value|
|--|--|
|GitHub Actions Settings|Enable|
|GitHub Account|Authorize -> Follow this instruction: wvanheemstra|
|Organization|vanHeemstraSystems|
|Repository|building-intelligent-cloud-applications|
|Branch|main|

Workflow Configuration:

```
# Docs for the Azure Web Apps Deploy action: https://github.com/azure/functions-action
# More GitHub Actions for Azure: https://github.com/Azure/actions
# More info on Python, GitHub Actions, and Azure Functions: https://aka.ms/python-webapps-actions

name: Build and deploy Python project to Azure Function App - python-faas

on:
  push:
    branches:
      - main
  workflow_dispatch:

env:
  AZURE_FUNCTIONAPP_PACKAGE_PATH: '.' # set this to the path to your web app project, defaults to the repository root
  PYTHON_VERSION: '3.10' # set this to the python version to use (supports 3.6, 3.7, 3.8)

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Setup Python version
        uses: actions/setup-python@v1
        with:
          python-version: ${{ env.PYTHON_VERSION }}

      - name: Create and start virtual environment
        run: |
          python -m venv venv
          source venv/bin/activate

      - name: Install dependencies
        run: pip install -r requirements.txt
        
      # Optional: Add step to run tests here

      - name: Upload artifact for deployment job
        uses: actions/upload-artifact@v2
        with:
          name: python-app
          path: |
            . 
            !venv/

  deploy:
    runs-on: ubuntu-latest
    needs: build
    environment:
      name: 'production'
      url: ${{ steps.deploy-to-function.outputs.webapp-url }}

    steps:
      - name: Download artifact from build job
        uses: actions/download-artifact@v2
        with:
          name: python-app
          path: .

      - name: 'Deploy to Azure Functions'
        uses: Azure/functions-action@v1
        id: deploy-to-function
        with:
          app-name: 'python-faas'
          slot-name: 'production'
          package: ${{ env.AZURE_FUNCTIONAPP_PACKAGE_PATH }}
          publish-profile: ${{ secrets.AzureAppService_PublishProfile_1234 }}
          scm-do-build-during-deployment: true
          enable-oryx-build: true
```

.github/workflows/main-python-faas(production).yml

Choose **Next:Tags >**

|Name|Value|Resource|
|--|--|--|
|project|python-faas|5 selected|

Choose **Next:Review + Create >**

### Summary

Function App by Microsoft

|Details||
|--|--|
|Subscription|b94dca1d-3277-4aa8-b826-1b4324072838|
|Resource Group|python-faas|
|Name|python-faas|
|Runtime stack|Python 3.10|
|Tags|project: python-faas|

|Hosting||
|--|--|

|Storage (New)||
|--|--|
|Storage account|pythonfaasbc70|
|Tags|project: python-faas|

|Plan (New)||
|--|--|
|Hosting options and plans|Consumption (Serverless)|
|Name|ASP-pythonfaas-9263|
|Operating System|Linux|
|Region|West Europe|
|SKU|Dynamic|
|Tags|project: python-faas|

|Monitoring (New)||
|--|--|
|Application Insights|Enabled|
|Name|python-faas|
|Region|West Europe|
|Tags|project: python-faas|

|Deployment||
|--|--|
|Continuous deployment|Enabled|
|GitHub account|wvanheemstra|
|Organization|vanHeemstraSystems|
|Repository|building-intelligent-cloud-applications|
|Branch|main|

Template for automation:

```
...
```

## 400  - Conclusion
