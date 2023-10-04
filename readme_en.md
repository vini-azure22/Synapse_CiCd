<h1>Implementation of CI/CD Pipeline (Continuous Integration/Continuous Delivery)
</h1> <p align="justify">CI/CD is a comprehensive term that covers various phases of DevOps. CI (Continuous Integration) is the practice of integrating code changes into a repository multiple times a day. CD has two meanings: Continuous Delivery automates code integrations,
while Continuous Deployment automatically releases final builds to end users. Frequent CI/CD testing reduces errors and code defects, making them essential for any workflow.</p>

## Document Contents
  * Authors
  * Overview
  * Prerequisites
  * Configuration
  * Usage
  * License

## Autors:
Bruno Andrade<br>
Raphael Freixo<br>
Vinícius Peters<br>

## Overview
<p align="justify">The implementation of the CI/CD pipeline is necessary to streamline and standardize the structure of your environment, ensuring the quality of code from the development environment to its implementation in the production environment, which is done automatically after the approval of artifacts. This document contains the procedure to implement this CI/CD structure using Github Actions and the Azure environment.</p>


## Prerequisites:
  * Have a service user with access permission to Synapse.
  * GitHub account with a created repository.
  * READER permission on the resource group.
  * CONTRIBUTOR permission on Synapse-Production.
  * Grant permission from the Service Principal.
  * Have a Development (DEV) and Production (PROD) Synapse environment.


## Github Configuration:
<p align="justify"> In your Github repository, click on <strong>creating a new file<strong>.</p>
<kbd> 
<br><br> 
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/2bcd8beb-74ce-44de-b009-942da3b396f7">
</kbd> 
<br><br><br> 
<p align="justify"> In the file path, create a file called "readme.yml" in the following folder structure ".github/workflows/readme.yml". Once this is done, click on <strong>Commit Changes...<strong></p> 
<kbd> 
<br><br>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/209a8179-1f60-4bdf-9296-83b945302282">
</kbd> 
<br><br><br> 
<p align="justify"> 1) Linking environment to git-hub actions: Open Synapse-DEV, select the option <strong>MANAGE</strong> and then the last option of git-configuration, as shown in the image below:</p> 
<br> 
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/73370525-6b2a-4296-845d-fd1a42bec98e"> 
</kbd> 
<br><br>

Then, select the Configure button in the middle of the screen.
<br><br>

In Repository Type, select GitHub and then enter the account owner's name: <br><br> <kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/4ee41b11-3399-4efa-886c-7212d6c1cbe7"> </kbd> <br><br>
Select the desired repository and all fields will be automatically filled. Do not change any configurations and click Apply.<br>
<br><br>

<kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/7c0df6f0-4302-42fc-bcd6-fd04bb5537b3"> </kbd> <br><br>
To create a new branch, on the top left corner, click on main branch and then click on New Branch[Alt+N].
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/df7cc483-ac19-449d-8fac-f763ecfc1e06">
</kbd>
<br><br>
Enter a name for your branch and create it as shown in the example below. Then, click on Create.
<kbd>
</strong>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/c2eb2066-48b3-47d9-a3df-8d35217d3bc1">
</kbd>
<br><br>

<p align="justify">To create the branch <strong>workspace_publish</strong>, we first need to publish it in Synapse DEV. In the same branch you just created, create a pipeline with a 
<strong>Set variable</strong> activity and create a variable. Once created, click on <strong>Commit all</strong>.
</p> 
<kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/8f5218fc-bf90-404c-9846-041de95a6b1b">
</kbd> 
<br><br> After that, click on <strong>OK</strong>.
<br> 
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/bcfc6147-3a8d-4983-9672-0e7adfdf3f7c"> 
</kbd> 
<br><br> <p align="justify">Once that is done, you will need to create a Pull Request. To do that, click on the name of your created branch in the top left corner and look for <strong>Create pull request[Alt+P]</strong></p>.
<kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/78303962-1a98-4a33-935a-fe5ff84eb807">
</kbd>
<br><br> <p align="justify">Open your Github repository, click on <strong>Create pull request</strong> or <strong>Compare & pull request</strong> as shown in the image below:</p> 
<kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/ce4c682d-a0ed-4eb4-948c-209e7afcebcd"> 
</kbd>
<br><br> An "Open a pull request" tab will open. Click on <strong>Create pull request</strong>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/f9628d4c-4ab9-4de1-bb6c-4618b811dc55"> 
</kbd> 
<br><br> 
<strong>Confirm merge</strong>.
<br> 
<kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/632e7013-3f1a-4c6f-8180-a6dfbf98b5da">
</kbd>
<br><br> After completing the previous steps, now open your <strong>main branch</strong> and click on <strong>Publish</strong>. 
<kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/812bc13a-e59b-4875-951a-9d3646588732">
</kbd>

## Github Repository Settings
<p align="justify">First, make an initial publication in the Synapse DEV environment so that Github creates a branch called "Workspace_publish". Inside your GitHub account, in the Synapse repository and in the workspace-publish folder, create a folder structure following this pattern: .github/workflows/</p>
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/66cf6c3c-05d4-4301-8a01-449b9ab72fdb">
</kbd>
<br><br>

And at the end, place the file with the environment parameters, in this case, the syn-deploy.yml file should be placed following the path shown in the image above.

<p align="justify">Inside the .yml file, you should adjust the three lines "TemplateFile", "ParametersFile", and "OverrideArmParameters" with the name of your workspace, as shown in the image below, highlighted in red. Considering my created workspace, it became "azure-test-dev". Note that the file contains lines that will be values inherited from Github Secrets (consider the ones with "${{secrets.____}}). These secrets will need to be assigned in Github</p> <br><br> <kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/f667ba78-7060-4cea-a2c3-c33ad6bd1c6a">
</kbd>
<br><br>

<p align="justify">The third line shown "OverrideArmParameters" does not need to be changed at this time, as we will create this file later and it can be ignored for now.</p>
  * WORKSPACENAME
  * RESOURCEGROUP
  * CLIENTID
  * CLIENTSECRET
  * SUBSCRIPTIONID
  * TENANTID
<br><br>
<kbd>
<img width="800" alt="MicrosoftTeams-image(18)" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/c085bbd7-fe34-4997-a51d-a4f1ff465fb8">
</kbd>
<br><br>

<p align="justify">After that, go to **settings**, and on the left side of the screen, go to **Secrets and variables > Actions**. In the "Secrets" tab, select **"New repository secret"**. In this repository, you will assign the value of the variables that will be inherited in the syn-deploy.yml file.</p> <br><br> <kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/a744988a-e72f-4b05-a720-bc482f50bd3c"> </kbd> <br><br>
Assign the name of the secret and the value. In this case, it will be assigned for each of these:

  * WORKSPACENAME
  * RESOURCEGROUP
  * CLIENTID
  * CLIENTSECRET
  * SUBSCRIPTIONID
  * TENANTID

For the SUBSCRIPTIONID, you should open your workspace, and then you will see the parameter:
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/4b24e1df-d45e-4078-9a2a-68f5df4e3089">
</kbd>

<p align="justify">For the **CLIENTID**, in the search bar, type App Registrations and click on it:</p> <br><br> <kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/2837fd29-dfea-4bdf-ad58-15f1bca46545"><br><br> </kbd> <br><br> After that, you need to create a user that will be assigned permissions in the next steps:<br><br> <br><br> <kbd> <img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/b20c0112-58c8-4e79-9e71-c353a8ca292a"><br> </kbd> <br><br> In the All applications tab, you will find the created user and its **CLIENTID**:<br><br> <kbd> <img width="1000" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/647496ae-abd9-4b8e-b361-5133fd89ba52"><br> </kbd> <br><br> To find the **TENANTID**, click on the created user in the previous step. In the example, click on USER-GIT<br> <kbd> <img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/ee568520-d1e3-489d-980d-fbc1a4a8b037"> </kbd> <br><br> For the **CLIENTSECRET**, still in the previous step, in the left side option bar, you will find the option *Certificates & secrets*. After clicking on this option, click on **+New client secret** and create an identity: <br> <kbd> <img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/e519d68a-3a76-4f70-87bf-9282abb17059"> </kbd> <br>
Put a description of your preference, and in the field below, you can leave it at 90 days by default. After doing this, you can click on Add and then go back to the previous page:
<br><br>
<kbd>
<img width="1000"  height="500" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/610c3c7e-1c7c-4ade-9aff-cc3ceea9001c">
</kbd>
<br><br>

With all the parameters filled, go to your Production Synapse workspace and go to the Access Control (IAM) options and click on Role assignment, as shown in the image below:

<br><br>
<kbd>
<img width="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/cf32881b-888f-4fe5-b540-4233213000e5">
</kbd>
<br><br>

Select the first option of Reader and then click on Next
<br><br>
<kbd>
<img width="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/8fb1e6b7-ef91-4780-8866-68976ceaec79">
</kbd>
<br><br>
After that, click on the Select Members option to select the user to grant Reader permission to the Resource Group:
<br>
<kbd>
<img width="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/ded5985b-e1ae-4bac-9d5a-85d70ab0b71d">
</kbd>
<br><br>


After creating the READER permission, open the Production Synapse and access the Access Control (IAM) in exactly the same way as in the previous step, but now grant Contributor permission to the production workspace.

Then, click on Role Assignment again and then on Add. Next, select Privileged Administrator roles as shown in the image below:
<br><br>
<kbd>
<img width="2100" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/17ac8e05-548e-441c-ac16-700e4895e228">
</kbd>
<br><br>

Click on Select Members and choose the user to apply this Contributor permission to:
<br><br>
<kbd>
<img width="1000" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/3ad9c74b-584a-46d7-8c26-330fed09ddd3">
</kbd>
<br><br>

After these steps, you will have the user with Reader permissions on the resource group and Contributor permissions on the production workspace.

Finally, open Synapse Studio, access the Manage option on the left sidebar:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/a0778f1c-5cd7-4c39-bafd-4095eaa669ad">
</kbd>
<br><br>

After that, go to Access Control in the left sidebar menu and click on Add to assign the Artifact Editor role to the previously created user. In the lower bar, select the user you want to assign it to:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/3437f11a-f249-4ae7-bd22-72c9e5d19ea8">
</kbd>
<br><br>

Configure Azure Key Vault
A Key Vault should be created for each Synapse DEV and PROD environment.

Step 1: In your Synapse account, go to the search bar and type Key Vault, and then click on Create
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/aea32c73-2fe9-45eb-a110-48ab4b651220">
</kbd>
<br><br>
After that, fill in the key vault creation information by assigning the resource group that was created in the Synapse Development. Then, go to Next and Review+Create.
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/a0f521a5-f8f3-4249-96c0-28d95324c963">
</kbd>
<br><br>
After granting the user permission to create Secrets within the Key Vault, create the secrets with the same name as the .yml file from the previous steps. (Provide further details).
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/8ac96d49-fed9-4748-91bd-32e353bdbe3a">
</kbd>
<br><br>
Note: All of these steps should also be done for the PRD environment with some exceptions we will see below.

For the production environment, you should follow the steps below:

Go to the Key Vault, click on the left sidebar on Access Control (IAM) and then open Role Assignments and look for KEY VAULT SECRETS OFFICER. Then, click on Next:
<br><br>
<kbd>
<img width="1600" height="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/c4b6a4d2-ec4e-4dda-b556-a6558701b14b">
</kbd>
<br><br>
After that, go to Members and in the Assign access to option, select "Managed identity". Once selected, click on +Select Members.
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/1eee6650-428e-4f7d-8938-018bfe8ae37c">
</kbd>
<br><br>
Select your subscription. In Managed Identity, select Synapse workspace(). After that, select your Production Synapse environment.
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/88f5b025-1cc9-4a15-9067-27d47966a824)">
</kbd>
<br><br>

Now your permission has been assigned to the production environment.

The next step is to publish something again in DEV with the Key Vault properly created. After that, you should open your TemplateWorkspace file and find the name of the KV that was automatically generated (usually created on line 20) as shown below:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/5e431ae6-8f16-4de0-b4d4-d98653faceb9">
</kbd>
<br><br>
After finding these parameters, create a file called ParameterPRD.json inside your DEV workspace folder and paste these parameters in key-value format:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/971224ab-0932-41ca-9363-bb2fc46a809c">
</kbd>
<br><br>
After doing this, you should go back to your .yaml file and in the "OverrideArmParameters" line, you should fill it with the name of your workspace and the name of the file you created called: ParameterPRD.json as shown in the image below:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/36ea49af-9b94-4716-94a3-989a24090f23">
</kbd>
<br><br>

## Usability
In your Development environment branch after making changes, the process to take them to production will follow these steps:

Commit your changes. In the example below, we will use "Pipeline 2," which does not exist in production:
<br><br>
<kbd>
<img width="587" alt="imagem1" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/30d26293-38b7-444c-8700-d30f4635f8d8">
</kbd>
<br><br><br>
2) Create a pull request to the main branch. In the example, it's the "main branch":
<br><br>
<kbd>
<img width="202" alt="MicrosoftTeams-image (40)" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/87d75eeb-ae2c-4c42-b63e-62ec5de195fa">
</kbd>
<br><br><br>
3) After your Pull Request is approved, the "main branch" will have all your changes. Therefore, the person responsible for the Pull Request should click on Publish as shown in the image below:
<br><br>
<kbd>
<img width="310" alt="IMAGEM3" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/00ed549b-3752-4a26-a5d2-05dbecb80805">
</kbd>
<br><br><br>
4) Wait until the success message appears on your screen:
<br><br>
<kbd>
<img width="957" alt="IMAGEM4" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/90c860d6-0638-4854-afb7-aac06e062e5a">
</kbd>
<br><br><br>
5) After that, go to the production environment, and you will see your changes in the production environment:
<br><br>
<kbd>
<img width="400" alt="IMAGEM5" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/cb77a586-d007-4661-8598-918092041f05">
</kbd>
<br><br><br>
<br><br><br>

## License
This project is made available under the terms of the MIT License.

Copyright 2023 Ernst & Young (EY)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.


















