---
layout: post
title: "Azure Series: Publish A Very Basic App To GitHub"
date: 2017-03-28
---

The purpose of this series is to walk through how to create a CI/CD pipeline using:
- Visual Studio
- Visual Studio Team Services
- Azure
- Terraform

## Install software and create accounts

Before we get started you need to install some software and create some accounts:
- Install Visual Studio Community Edition
 __[Visual Studio](https://visualstudio.microsoft.com/vs/community/)__
- Create a free account on Visual Studio Team Services
 __[VSTS](https://visualstudio.microsoft.com/team-services/)__
- Create a free account on Azure 
 __[Azure](https://azure.microsoft.com/en-us/)__
- Create a free account on GitHub
 __[GITHUB](https://github.com/)__
- Download Terraform
 __[Terraform](https://www.terraform.io/downloads.html)__

As a consistent naming convention we are going to call:

| Element | Name |
| :------ | ----------- |
| Resource Group   |TestWebAppRG |
| App Service   |TestWebApp0101 |




## Create a GitHub Repository

- Login to your GitHub account which you created earlier.

- Select the "+" at the top right hand side of GitHub.

<img src="/images/Create-GitHub-Repo-01-01.png" alt="drawing" width="400px"/>

- Give the repository a name:

<img src="/images/Create-GitHub-Repo-02-01.png" alt="drawing" width="400px"/>

- Make a note of the link as we will use this later:

<img src="/images/Create-GitHub-Repo-03-01.png" alt="drawing" width="400px"/>


## Create an Azure Resource Group & App Service

- You can find resource group by searching the Marketplace

<img src="/images/Create-Resource-Group-01-01.png" alt="drawing" width="400px"/>

- Select Resource group

<img src="/images/Create-Resource-Group-02-01.png" alt="drawing" width="400px"/>

- Give the Resource Group a name of __TestWebAppRG__

<img src="/images/Create-Resource-Group-03-01.png" alt="drawing" width="400px"/>

## Create a basic Visual Studio Application

- Create a new project

<img src="/images/Create-VS-Project-01.png" alt="drawing" width="400px"/>

- Create an ASP.NET Web Application

<img src="/images/Create-VS-Project-02.png" alt="drawing" width="400px"/>

- Leave it empty as we will add a basic HTML page to it

<img src="/images/Create-VS-Project-03.png" alt="drawing" width="400px"/>

- From Solution context menu select Add and select HTML page

<img src="/images/Create-VS-Project-05.png" alt="drawing" width="400px"/>

- Name it index.html

<img src="/images/Create-VS-Project-06.png" alt="drawing" width="400px"/>

- Add "Hello World" to it

<img src="/images/Create-VS-Project-07.png" alt="drawing" width="400px"/>

## Lets push it to GitHub

- Right click on your solution and select Commit

<img src="/images/Add-Project-To-Git-01-01.png" alt="drawing" width="400px"/>

- Enter a comment for this initial commit 

<img src="/images/Add-Project-To-Git-02-01.png" alt="drawing" width="400px"/>

- Select Sync

<img src="/images/Add-Project-To-Git-05-01.png" alt="drawing" width="400px"/>

- Select Publish to Git Repo

<img src="/images/Add-Project-To-Git-06-01.png" alt="drawing" width="400px"/>

- Enter the URL to the git repository collected erlier

<img src="/images/Add-Project-To-Git-07-01.png" alt="drawing" width="400px"/>

- We can now see our files in GitHub

<img src="/images/Add-Project-To-Git-08-01.png" alt="drawing" width="400px"/>
