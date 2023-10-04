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




























