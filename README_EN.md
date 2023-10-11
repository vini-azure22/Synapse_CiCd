## Escolha o idioma / Choose the language
- [Português (BR)](README_PT.md)
- [English](README_EN.md)


## Implementation of CI/CD Pipeline (Continuous Integration/Continuous Delivery)
<p align="justify"> CI/CD is a comprehensive term that covers various phases of DevOps. CI (Continuous Integration) is the practice of integrating code changes into a repository multiple times a day. CD has two meanings: Continuous Delivery automates code integrations,
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

    
## Configuration
### File readme.yml

<p align="justify"> In your Github repository in the code tab, click on <strong>creating a new file<strong>.</p>
<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/8c8d9fec-6558-46de-bd87-b242761201b2">
</kbd>
<br><br><br>
<p align="justify"> In the file path, create a file called "readme.yml" in the following folder structure ".github/workflows/readme.yml". Once this is done, click on <strong>Commit Changes...<strong></p> 

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/458bf186-78cd-4342-a029-c3104fbe7d0d">
</kbd>
<br><br><br>

### Link Synapse to Github
<p align="justify">Open Synapse DEV,  and from the icons on the left select <strong>Manage</strong> and then, select the last option <strong>Git configuration</strong>. Then, select the <strong>Configure</strong> button in the middle of the screen.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/37c1f94b-42c6-4e83-a255-68ba541a3bdd">
</kbd>
<br><br><br>
<p align="justify">In <strong>Repository Type</strong>, select GitHub and in <strong>Github repository owner</strong>, enter the account owner's name.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/f1bb8a5c-6386-47f1-b810-8bffa2295fc0">
</kbd>
<br><br><br>
<p align="justify"> In <strong>Repository name</strong>, select the desired repository. For the other fields do not change any configurations and click <strong>Apply</strong>.</p>


<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/1cfc4ead-533c-495e-b3c8-ae4f6ffb4797">
</kbd>
<br><br><br>

### Create a New Branch
<p align="justify">On the top left corner,click on<strong>New Branch[Alt+N]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b6eae871-548d-45b0-9d9b-b830867b136e">
</kbd>
<br><br><br>

<p align="justify">Enter a name for your branch  create it based on main branch as shown in the example below. Then, click on <strong>Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/85476c8e-564d-45ab-8e91-5cc8b19a8746">
</kbd>
<br><br><br>

### Workspace_publish
<p align="justify">The workspace_publish branch will be created automatically after being done a publish in Synapse DEV. To do that, make a publish to the same branch you created. Create a pipeline with a <strong>Set variable</strong> activity and create a variable. Once created, click on<strong>Commit all</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/0309cb13-331f-4177-ad67-69c03766dbc2">
</kbd>
<br><br><br>

Click on <strong>OK</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/f0dff78e-d2dc-4496-9cb3-ddf9050ba184">
</kbd>
<br><br><br>
<p align="justify">Once that is done, you will need to create a <strong>Pull Request</strong>. To do that, click on the name of your created branch in the top left corner and look for <strong>Create pull request[Alt+P]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/4e40305d-5c04-4f8c-b086-7a875a8875db">
</kbd>
<br><br><br>
<strong>OBS:In the following steps, you can only approve a pull request if you're the approver. Otherwise, make a request to the approver.</strong>
<br><br>

<p align="justify">Open your Github repository, click on <strong>Create pull request</strong> or <strong>Compare & pull request</strong>  as shown in the image below.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/7baaf7ee-e2a5-47c4-8b67-e813bc5bdb91">
</kbd>
<br><br><br>

<p align="justify">An "Open a pull request" tab will open. Click on <strong>Create pull request</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/cffdd34b-75ad-4015-872f-bb0e1da90c16">
</kbd>
<br><br><br>

<strong>Merge pull request</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/77176f83-e2bf-417d-b7d6-7294fd7187d8">
</kbd>
<br><br><br>

<strong>Confirm merge</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/d495a227-b8f8-4a44-b94b-a474a15047c3">
</kbd>
<br><br><br>

After completing the previous steps, now open your <strong>main branch</strong> and click on <strong>Publish</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5af27bb7-0c7a-406b-8a7a-58ca23d0a5b5">
</kbd>
<br><br><br>

### Github Repository Settings

<p align="justify">Inside your GitHub repository, select the <strong>Code</strong> tab and search for <strong>workspace_publish</strong>. Create a folder structure following this pattern: <strong>.github/workflows/syn-deploy.yml</strong></p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/6d37a2f2-c0ba-4598-bee4-4a0178e769b8">
</kbd>
<br><br><br>
<p align="justify"> And at the end, place the file with the environment parameters, in this case, <strong>syn-deploy.yml</strong>file should be placed following the path shown in the image above.</p>


### Configuring syn-deploy.yml File
<p align="justify">Inside the <strong>syn-deploy.yml</strong> file, adjust the three lines <strong>TemplateFile,ParametersFile e OverrideArmParameters</strong> with the name of your workspace, as shown in the image below, highlighted in red. Note that the file contains lines that will be values inherited from Github Secrets (consider the ones with "${{secrets.____}}). These secrets will need to be assigned in Github</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/a1db97c6-ee99-4518-bee0-01c1538be158">
</kbd>
<br><br><br>
These will be the parameters that will be inherited from Github:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/3d0cc300-90c0-4a60-8687-7974e15ea677">
</kbd>
<br><br><br>

### Configuring Secrets Github

Go to <strong>Settings</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/430172cd-0aa1-49ca-b124-6b21e06da60b">
</kbd>
<br><br><br>
<p align="justify">On the left side of the screen, go to <strong>Secrets and variables</strong> and <strong>Actions</strong>. In the <strong>Secrets</strong> tab, select <strong>New repository secret</strong>.In this repository, you will assign the value of the variables that will be inherited in the <strong>syn-deploy.yml</strong> file.</p>


<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/862df26c-21c7-4042-a1a4-6eb939f36ada">
</kbd>
<br><br><br>
<strong>It is worth mentioning that all these parameters must be filled in with the data from the Production environment.</strong>

Assign the name of the secret and the value. In this case, it will be assigned to each of these:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

Example:<br>
<strong>Name</strong> = WORKSPACENAME<br>
<strong>Secret</strong> = your workspace name<br>

Then, click on <strong>Add secret</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/28f720e4-f015-468f-b9a2-d86a6f9de088">
</kbd>
<br><br><br>

### How to Find Each of the Parameters

To find the parameters:<br>
* <strong>WORKSPACENAME</strong><br>
* <strong>RESOURCEGROUP</strong><br>
* <strong>SUBSCRIPTIONID</strong><br>

<p align="justify">In Azure Portal, search for your production Synapse workspace. On the left tab, go to <strong>Overview</strong> and you will find the information for the three parameters listed above.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/44f345af-3469-45a3-8ef2-728bc970378e">
</kbd>
<br><br><br>

To find the parameters:<br>
<strong>CLIENTID</strong><br>
<strong>CLIENTSECRET</strong><br>
<strong>TENANTID</strong><br>

<p align="justify">A service principal should be created.In the search bar, type <strong>App Registrations</strong> and click on it.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/874f9d93-f936-49cc-b393-8f909ab473f3">
</kbd>
<br><br><br>
After that, click on <strong>+New registration</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/d4d36c8e-b861-474b-897b-232bba9a14c3">
</kbd>
<br><br><br>
After that, assign any name and press <strong>Register</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/3bd0606b-3133-4f94-a2cc-7899ed96fb85">
</kbd>
<br><br><br>

<p align="justify">Once created, you will be taken to the <strong>Overview</strong> page of the service principal. Here, you will find the <strong>CLIENTID</strong> and <strong>TENANTID</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/dae17adb-f935-4e4e-8893-1e0b3df5920e">
</kbd>
<br><br><br>
<p align="justify">For the <strong>CLIENTSECRET</strong>, in the left side option bar, you will find the option <strong>Certificates & secrets</strong>. After clicking on this option, click on <strong>+ New client secret</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b26adf1e-5f56-4168-9f23-016cbe8a2457">
</kbd>
<br><br><br>
<p align="justify">In <strong>Description</strong> Put a description of your preference. Then, click on <strong> Add </strong>.</p>


<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5456a185-9831-4e96-b58b-36de8ce41e82">
</kbd>
<br><br><br>
<p align="justify">Once created, it will appear in the <strong>Value</strong> column the <strong>CLIENTSECRET</strong> value. Record this value, it will <strong>only appear once and you will not be able to see it again!</strong></p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b6962899-ed70-4051-9b61-0cc058093254">
</kbd>
<br><br><br>

### Assigning Permissions to the Service Principal

<p align="justify">With all the parameters filled in from the previous steps, sign in to your <strong>Production</strong> Synapse workspace and go to <strong>the Access Control (IAM)</strong> options and click on <strong> Role assignment</strong>.Look further up for the <strong>+ Add</strong> option. </p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/91469a4b-e253-4650-9e75-f406c3a3c67e">
</kbd>
<br><br><br>
<p align="justify">The Primary Service <strong>Reader permission</strong> will be assigned to the production resource group. To do this, select the first option of Reader and then <strong>Next</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/702faa15-d876-4d0e-9942-d80aad982b01">
</kbd>
<br><br><br>
<p align="justify">In Members tab, click on the <strong>+ Select members</strong> option. Use the search bar next to it to choose the user and click <strong>Select</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/a60ace36-9ff5-4fa8-ba0d-1d2ecf461a72">
</kbd>
<br><br><br>
After that, click on <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/6bac5d72-e8c6-4fd9-bbbc-ed244956aa88">
</kbd>
<br><br><br>
<p align="justify">Given the Reader permission, repeat the previous step, but now give the <strong>Contributor</strong> permission to the production workspace. Click <strong>Role Assigment</strong> and then <strong>click +Add</strong>.Select the Privileged Administrator roles tab, and click <strong>Contributor</strong>. Then click <strong>Next</strong>.</p>


<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/e1c1db92-0fee-4c87-9eab-99f1c5a3b1c2">
</kbd>
<br><br><br>
<p align="justify"> Members tab, click <strong>+Select members</strong> and select the user to apply the <strong>Contributor</strong> permission to.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/4040398a-e1ef-488e-bd52-077ec49819d1">
</kbd>
<br><br><br>

Click <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/0629429c-3868-4f6a-9749-171204867430">
</kbd>
<br><br><br>

Finally, open Production Synapse Studio.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5d757a3c-2ff6-429d-93f2-04be234c528b">
</kbd>
<br><br><br>
<p align="justify">Go to the <strong>Manage</strong> option on the left side and <strong>Access control</strong>. Click <strong>+ Add</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/bdb79faa-e708-4e22-9381-47d1c8d86374">
</kbd>
<br><br><br>
<p align="justify"Select the <strong>Synapse Artifact Publisher</strong> role. On the bottom bar, you must select the Service Principal user you previously created and click <strong>Apply</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/ca292ec5-8f1b-49c5-8d8b-e8a5fe8db85b">
</kbd>
<br><br><br>

### Configure Azure Key Vault

<strong>A Key Vault should be created for each Synapse DEV and PROD environment.</strong>

In portal Azure, go to the search bar and type <strong>Key Vaults</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b2512f47-2b02-4960-8622-6c012d820d1b">
</kbd>
<br><br><br>
Click <strong>+Create</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/8845731d-e5ab-407f-bd7f-822e70e7398b">
</kbd>
<br><br><br>
<p align="justify">After that, fill in the key vault creation information by assigning the resource group that was created in the Synapse Development. Then, go to <strong>Review+Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/fc74c4e3-1903-46e7-99f2-ab79b12016c0">
</kbd>
<br><br><br>
<p align="justify">In production Key Vault, click on the left side <strong>Access Control(IAM),</strong> click <strong>+Add</strong> and then click <strong>Add role assignment</strong>.</p>


<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/1973a791-e2ef-419e-8b50-f1a4a032b977">
</kbd>
<br><br><br>
In <strong>Role Assignments,</strong> look for <strong>Key Vault Secrets Officer</strong>. Then click <strong>Next</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/d7ce34e8-d6ec-4808-ad38-66dc2cab74b3">
</kbd>
<br><br><br>
<p align="justify">After that, go to Members and in the <strong>Assign access to</strong> option, select <strong>Managed identity</strong>. Once selected, click on <strong>+Select Members</strong>.</p>

In <strong>Managed Identity</strong> select Synapse workspace(). After that, select your Production Synapse environment.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/3558faa7-475d-42e0-a39d-69a8b9de4533">
</kbd>
<br><br><br>

### Configure Linked Service

In your DEV Workspace, go to <strong>Manage/<strong> and <strong>Linked services</strong>. Click <strong>+ New</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5a679cf7-4de5-4a6a-8d6e-3d917286f6f5">
</kbd>
<br><br><br>
In the search bar, search for <strong>Azure Key Vault</strong> and click <strong>Continue</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b104286e-89bf-4eb6-9c42-43dd03c86717">
</kbd>
<br><br><br>
<strong>Name:</strong>  Give Key Vault a name.<br>
<strong>Azure Subscription:</strong> Select your subscription.<br>
<strong>Azure Key Vault name:</strong> Select the Key Vault created from the production environment.<br>

For the others, leave it default. After that, press <strong>Commit</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/9798d961-e003-437b-ab52-3418801650e7">
</kbd>
<br><br><br>
<p align="justify"> The next step you will need to publish something again in DEV with the Linked Service properly created (repeat the step in topic Workspace_publish).</p>


<p align="justify">After that, you will have to enter your <strong>TemplateWorkspace.json</strong> file and search for the KV name that was automatically generated as shown below:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/6e5ec722-dffe-4d55-93dd-d54bc019333c">
</kbd>
<br><br><br>
<p align="justify">  Copy the "LS_KV_DEV_properties_typeProperties_baseUrl" and <strong>the defaultValue</strong>. They will be used in the next step for creating the <strong>ParameterPRD.json file</strong>.

### Creating ParameterPRD.json file

<p align="justify"> In your Github repository, create a file named <strong>ParameterPRD.json</strong> inside your DEV workspace folder and paste the previously copied parameters into the following format:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/ea247b74-ef31-4cd2-8f02-db88b4a687c4">
</kbd>
<br><br><br>
<p align="justify"> For the name of the <strong>ParameterPRD.json</strong> file, make sure that the is exactly the same as the name that is in the <strong>syn-deploy.yml</strong> file in <strong>OverrideArmParameters</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/a444a571-a19d-4a5d-a6c6-2a7f6bb9ef47">
</kbd>
<br><br><br>

## Usage

<p align="justify"> In your Development environment branch after making changes, the process to take them to <strong>production</strong> will follow these steps:</p>

<p align="justify"><strong>Commit</strong> your changes. In the example below, we will use "Pipeline 2" in the product branch:

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/ea4ee1d9-f5d6-40fe-aaff-9fe60319c172">
</kbd>
<br><br><br>
<p align="justify"> Create a <strong>Pull request</strong> to the main branch.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/39fdce80-ef09-4dc4-96b2-fff79d89f8bb">
</kbd>
<br><br><br>
<p align="justify"> After your<strong>Pull request is approved</strong>, the main branch will have all your changes. Therefore, the person responsible for the Pull Request should click on Publish as shown in the image below:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/446f7b39-5895-4bea-bc40-59dc0f33143d">
</kbd>
<br><br><br>
<p align="justify"> Wait until the success message appears on your screen:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/61eaaf62-8bbf-4f6f-8d36-c33040784d6a">
</kbd>
<br><br><br>
<p align="justify"> After that, go to the <strong>production</strong> environment and you will see your changes in the production environment:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/2285cf81-68b5-4c93-a704-1defcd49571d">
</kbd>
<br><br><br>
CI/CD finished!
